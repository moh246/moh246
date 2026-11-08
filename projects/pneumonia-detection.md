# Pneumonia Detection from Chest X-rays

Medical imaging · Udacity AI for Healthcare Nanodegree

## Problem

Detect pneumonia on frontal chest X-rays as a triage aid: flag likely cases so a radiologist reads them first. Pneumonia is rare in the NIH ChestX-ray14 dataset (about 1.3% of 112,120 images), it usually appears alongside look-alike findings, and the labels were mined from radiology reports by NLP, so they're noisy.

## What I built

- **Data exploration** of demographics, view positions, co-occurring findings and pixel intensities. It showed how imbalanced the data is and how often pneumonia overlaps with infiltration, edema and effusion.
- **Split by patient** (80/20, stratified), so no patient appears in both sets. Training was balanced 50/50. Validation was kept at about 20% pneumonia, closer to a clinic where pneumonia is suspected, so the precision is realistic.
- **VGG16** pre-trained on ImageNet: blocks 1–4 frozen, block 5 fine-tuned, a new dense head with dropout. Augmentation on training data only.
- **Threshold chosen on validation** to maximise F1, since a triage tool has to balance missed cases against false alarms.
- **Subgroup analysis** by sex, age, view and co-occurring findings.
- **DICOM inference** that checks the header first (modality DX, body part CHEST, position PA or AP) and rejects anything else before predicting.
- **An FDA-style submission:** intended use, limitations, ground truth and a validation plan.

## Result

On 1,435 validation images (20% pneumonia):

| AUC | F1 | Recall | Precision | Specificity |
|---|---|---|---|---|
| 0.702 | **0.440** | 0.624 | 0.340 | 0.697 |

For context, the CheXNet paper reports an average F1 of 0.387 for practising radiologists on this task. The subgroup analysis found real limits: sensitivity is 0.78 on AP views but 0.43 on PA views, and studies with edema or effusion cause many false positives.

**Code:** [pneumonia-detection-xray](https://github.com/moh246/pneumonia-detection-xray)

## Stack

Keras/TensorFlow · VGG16 · pydicom · scikit-learn · pandas

[← Back to profile](../README.md)
