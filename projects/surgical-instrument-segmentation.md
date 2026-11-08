# Surgical Instrument Segmentation

Medical imaging · Surgical instrument segmentation

## Problem

This started as a take-home task: binary segmentation of surgical instruments on **[EndoVis-17](https://www.kaggle.com/datasets/aithammadiabdellatif/binarysegmentation-endovis-17)**, robotic surgery video with about 525 frames from 4 operations.

My first clean run scored **Dice 0.000**. The loss curve was smooth and nothing crashed. A crash would have been easy to find; this failure was silent. So I stopped tuning the model and audited the data.

## What I built

### 1. A data audit with integrity guards

The archive had four traps. None of them crash, and each one quietly corrupts either the labels or the evaluation:

1. **Masks in different encodings.** Some mark the instrument as 255, others as 1. The usual `mask > 127` turned the 1-style masks completely black, so the model trained against empty ground truth. That was the Dice 0.000. The fix is one character: `mask > 0`.
2. **43% of filenames had no video ID.** I worked out which surgery each frame came from using frame numbering and an image fingerprint, after checking the fingerprint on videos I already knew.
3. **Mixed JPEG and PNG.** Without handling, the model could learn compression artefacts instead of instruments, so I added JPEG-compression augmentation.
4. **One surgery split across two naming styles.** Its near-identical frames could have landed on both sides of the train/test split.

Every check is a guard that prints PASS or FAIL in a plain sentence. Expected failures are reported, never hidden.

### 2. The model

- **U-Net** with a pretrained ResNet-34 encoder. I also implemented the U-Net from scratch in PyTorch. The pretrained encoder is the default because there were only about 375 training frames.
- **A loss tuned to the error I measured.** On the worst frames the model traced the tool correctly, then kept colouring down the shaft. So I combined BCE with a Focal Tversky loss tilted to punish over-segmentation more than missed pixels. That raised precision noticeably for a small cost in recall.

### 3. Honest evaluation

- **Whole surgeries held out, never single frames.** At about 2 frames per second, neighbouring frames are nearly identical, so a random split inflates the score.
- **Threshold chosen on validation and frozen.** The test set is touched once.
- **Test-time augmentation** with flips.
- **Leave-one-surgery-out cross-validation** over all 4 videos, reported as mean ± spread. The videos differ by about 20 Dice points, so a single split is a coin flip.
- **A finding:** the score depends mostly on how thick the instruments are. Across the four videos, instrument area and precision correlate at +0.999. A thin-instrument video scores lower even with the same model.

**Code:** [surgical-instrument-segmentation](https://github.com/moh246/surgical-instrument-segmentation) has the notebook with the data audit, model and evaluation.

## Result

**Dice 0.846 ± 0.071, IoU 0.749 ± 0.099**, leave-one-surgery-out over 4 videos (per-video Dice from 0.780 to 0.933).

## Stack

PyTorch · U-Net (ResNet-34 encoder) · segmentation-models-pytorch · Albumentations

[← Back to profile](../README.md)
