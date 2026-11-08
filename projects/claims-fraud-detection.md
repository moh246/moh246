# Claims Fraud Detection

Health insurance · Fraud detection

## Problem

Fraudulent claims were getting paid out. The check had to happen before the money left, not after. And there were no ground-truth fraud labels to train on.

## What I built

- **Labels from deterministic rules.** Known impossible billing patterns became weak labels: procedure-demographic conflicts, repeats of procedures that can't repeat, geographic impossibilities. Only the rules a human would agree with without debate were used as labels. Statistical features stayed as inputs, because unusual isn't the same as fraudulent.
- **Features at four levels, from narrow to wide:**

  | Level | The question it asks | Example |
  |---|---|---|
  | Claim | Is this claim coherent on its own? | A pregnancy scan billed for a male member |
  | Provider | Is this provider unusual among its peers? | A clinic billing far more at the top level than similar clinics |
  | Member | Is this member unusual among similar members? | Several clinics in a few weeks for the same condition |
  | Relationship | Are a provider and a set of members linked more than they should be? | A large share of a provider's claims coming from a few members |

  The relationship features mattered most. Claims fraud is rarely one bad claim; it's a relationship that repeats.
- **An XGBoost model** trained on them, outputting a fraud probability.
- **Inline scoring in the claims flow, in three bands.** Every claim is scored before payout:
  - above 0.8: rejected automatically
  - 0.5 to 0.8: sent to the investigation team
  - below 0.5: paid normally

  The upper threshold was set by the cost of a wrong rejection, agreed with the business. The lower one was set by how many cases the investigators could actually review.

## Result

About **US$35,000 in fraudulent payouts prevented** over a 6-month production run. The money never left the company, so no recovery was needed.

## Stack

XGBoost · feature engineering · rule-based weak labelling

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
