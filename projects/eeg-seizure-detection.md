# EEG Seizure Detection and Prediction with Caregiver Alerts

Neurotech · EEG · IoT · BSc thesis · Team project

## Problem

A seizure detector is only useful if someone finds out in time. So the goal wasn't just to classify EEG, but to alert a caregiver when a seizure is coming.

## What we built

**Data:** the [CHB-MIT Scalp EEG dataset](https://physionet.org/content/chbmit/1.0.0/), recorded at 256 Hz. Experiments focused on patients 3, 12, 13 and 16.

**Preprocessing**

- Labelled each recording's windows from the seizure annotations
- Removed bad channels (EOG and NaN channels)
- Band-pass filtered at 0.5–30 Hz

**Features:** 13 per window, covering time, frequency and complexity: standard deviation, fractal dimension, Hurst exponent, kurtosis, skewness, fluctuation index, Hjorth mobility, mean, max and min absolute value, RMS, spectral centroid, and coefficient of variation.

**Model**

- Kept the features that separate the two classes, using a two-sample t-test
- Balanced the classes and normalised the features
- Trained an SVM with an RBF kernel in MATLAB on a 70/30 split of the windows

We also tried a published approach based on a surrogate channel from empirical mode decomposition, with power-spectral features on 1-second epochs.

**Caregiver alert:** a Python service streams each window's features to the trained model through the MATLAB engine. When a window is classified as a seizure, it sends a single notification and stays quiet until the state changes, so the caregiver isn't flooded with repeat alerts.

## Result

About **75% accuracy, 77% sensitivity and 75% specificity** across the experiments. The thesis was graded **A+**.

## Code

[eeg-seizure-detection](https://github.com/moh246/eeg-seizure-detection), forked from the team repository [Reem-Muhammad/GP](https://github.com/Reem-Muhammad/GP).

## Stack

MATLAB · SVM (RBF) · signal processing · Python · MATLAB Engine API · CHB-MIT

[Back to profile](../README.md)
