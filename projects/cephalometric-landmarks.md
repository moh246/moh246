# Cephalometric Landmark Loss Function

Medical imaging · Dental · Loss design

## Problem

Cephalometric analysis places 19 landmarks on a skull X-ray and measures the distances and angles between them. A model that predicts one heatmap per landmark is usually trained with a pixel-wise loss like MSE. That loss treats every landmark on its own, so it doesn't care whether the predicted landmarks keep the right geometry relative to each other.

The task was to implement a loss that also takes this anatomical context into account, from a formula given in the task spec, and get it training.

## What I built

- **An encoder–decoder network** that takes a 1-channel 512×512 X-ray and outputs 19 heatmaps, one per landmark.
- **The geometry-aware loss.** MSE between the predicted and ground-truth heatmaps, multiplied by a weight that measures how far off the geometry is:
  1. Take each landmark's position from the peak of its heatmap.
  2. Build a 19×19 matrix of distances between every pair of landmarks, and a 19×19 matrix of angles, for both the prediction and the ground truth.
  3. The weight is the log₂ of the Euclidean difference between the two distance matrices, plus the same for the two angle matrices.
- **Checks on every piece.** The first version of the loss came out as −inf (a log of zero), which blocks backpropagation, so I traced each sub-function line by line. I tested the loss on synthetic data first, then ran a training loop and printed the gradient norm of every layer to confirm gradients reach the whole network.

## Result

A working custom loss and training loop for 19-landmark heatmaps, tested end to end on synthetic data, with gradients reaching every layer. It wasn't trained on real cephalograms as part of this task.

## What I'd change next

The landmark positions come from a hard argmax, and the geometry weight is turned into a plain number before it multiplies the MSE. So the geometry term scales the loss but doesn't push the landmarks into place by itself. Swapping in a soft-argmax and keeping the weight as a tensor would make the geometry term fully differentiable.

## Stack

PyTorch · encoder–decoder CNN · custom loss

**Code:** [cephalometric-landmark-loss](https://github.com/moh246/cephalometric-landmark-loss)

[← Back to profile](../README.md)
