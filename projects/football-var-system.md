# Real-Time Football Video-Assistant System

Computer vision · Real-time video · Sports

## Problem

An offside decision needs to know where every player and the ball are **on the pitch**, not just in the image, and it has to keep up with live video. At broadcast frame rates the whole pipeline has roughly 40 ms per frame.

## What I built

Four components, each doing one job:

| Component | Job | Why that one |
|---|---|---|
| **YOLOv5** | Detect players and ball in every frame | Single-stage, one forward pass, so it fits the frame budget |
| **ByteTrack** | Keep each player's identity across frames | Keeps low-confidence detections instead of discarding them, which is what breaks tracking when players are partly hidden |
| **DETR** | Segment pitch regions and lines | Set prediction with no non-maximum suppression; it runs at a lower rate, so its extra cost is acceptable |
| **Homography** | Convert pixel positions to pitch coordinates | An offside call needs positions on the ground, not in the image |

How they fit together: detection finds what's in the frame, tracking says it's the same player across frames, segmentation gives the pitch lines, and the homography turns pixels into pitch coordinates. The pitch is a plane, so mapping from image to pitch is exactly a homography. It's estimated from the pitch line markings, whose real dimensions are known.

## Result

Shipped the first release as a Flask service.

What I took from it: working under a hard real-time constraint changes every architecture decision. A more accurate model that misses the frame budget is worthless.

## Stack

YOLOv5 · ByteTrack · DETR · homography · Flask

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
