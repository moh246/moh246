# paxflow

Medical imaging · Surgical instrument segmentation

## Problem

This started as a take-home task: segment surgical instruments in endoscopic video frames from **EndoVis-17**. A model alone doesn't get you far in a clinical setting, though. You also need standard output formats, traceability and monitoring. So I took it well past the brief.

## What I built

- **Model:** U-Net with a ResNet-34 encoder.
- **A 10-stage pipeline** around it, including:
  - FastAPI inference service
  - **DICOM SEG and SR output** via highdicom, so the results open in standard imaging tools
  - **Hash-chained audit ledger**, so every prediction can be traced and any tampering shows up
  - **PSI drift monitoring**, to catch when incoming data stops looking like the training data
  - **React review console** for a human to check the results
- **paxseg**, a separate validation framework for the model.

<!-- TODO: list all 10 pipeline stages if you want the full picture here. -->
<!-- TODO: is the code public? If yes, add the repo link here and in the README table. -->

## Result

**Dice ≈ 0.855** on EndoVis-17.

## Stack

U-Net (ResNet-34 encoder) · FastAPI · highdicom · DICOM SEG/SR · React

[← Back to profile](../README.md)
