# Cephalometric Landmark Detection

Medical imaging · Dental

## Problem

Cephalometric analysis depends on placing anatomical landmarks on skull X-rays. Doing that by hand is slow and varies from person to person.

<!-- TODO: check this problem line and add what the company needed specifically. -->

## What I built

- A **U-Net** that predicts landmark positions.
- A **custom anatomical-context loss**, so predictions also respect where landmarks sit relative to the surrounding anatomy, not just pixel by pixel.

<!-- TODO: which dataset, and how many landmarks? -->
<!-- TODO: one sentence on how the anatomical-context loss works. -->

## Result

<!-- TODO: add a metric, e.g. mean radial error (mm) or success detection rate within 2 mm. -->

## Stack

U-Net · custom loss

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
