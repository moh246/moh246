# Real-Time Football Video-Assistant System

Computer vision · Real-time video · Sports

## Problem

Offside decisions need to know where every player and the ball are on the pitch itself, not just in the camera image. It also has to keep up with live video.

## What I did

Built the first release of a real-time system that:

- finds the players and the ball in every frame,
- keeps track of who is who as they move and overlap,
- maps their positions from the camera image onto the pitch,

all within the time budget of a single video frame.

## Impact

- **First release shipped** as a service.
- What I took from it: a hard real-time limit changes every design decision. A more accurate model that misses the frame budget is useless.

---

The work belongs to the company and is under NDA, so this page covers the problem, my role and the impact only.

[← Back to profile](../README.md)

