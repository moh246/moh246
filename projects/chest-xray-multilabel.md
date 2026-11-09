# Chest X-ray Multi-label Classification

Medical imaging · Multi-label classification

## Problem

A single chest X-ray can show several findings at once, so the model has to predict multiple labels per image instead of a single class. The task was to build that end to end on the [NIH Chest X-ray dataset](https://www.kaggle.com/datasets/nih-chest-xrays/data): data exploration, a preprocessing pipeline, model selection, metrics, and a short deployment scenario.

## What I built

- A **DenseNet-121** multi-label classifier. It has been the standard chest X-ray baseline since CheXNet, so results stay comparable. Dense connections also help when data is limited.
- **Split by patient, not by image.** A patient can have several X-rays, and if they land on both sides of the split you're measuring memorisation. This is the most common way medical imaging results get inflated.
- **A 510(k)-style validation plan.** It fixes the acceptance criteria before the test result is seen, instead of tuning until the number looks good.
- **Served with FastAPI and containerised with Docker**, as a demo deployment.

## Result

**F1 0.83.** That's measured against labels extracted from radiology reports by NLP, not confirmed by a radiologist. So the ground truth itself is noisy, and the number should be read with that in mind.

## Stack

DenseNet-121 · NIH Chest X-ray · FastAPI · Docker

[Back to profile](../README.md)
