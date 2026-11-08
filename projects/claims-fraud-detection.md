# Claims Fraud Detection

Health insurance · Fraud detection

## Problem

Fraudulent claims were getting paid out. The check had to happen before the money left, not after.

## What I built

- **Engineered features** on the claims, with the fraud labels derived from those features.
- **An XGBoost model** trained on them.
- **Inline scoring in the claims flow.** Every claim is scored before payout, and flagged claims are rejected.

<!-- TODO: what kinds of features (provider behaviour, claim patterns, member history)? Keep it general if the details are confidential. -->

## Result

About **US$35,000 in fraudulent payouts prevented** over a 6-month production run.

## Stack

XGBoost · feature engineering

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
