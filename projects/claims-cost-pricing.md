# Risk-Based Pricing for Health Insurance Plans

Health insurance · Pricing

## Problem

Corporate health plans were priced on demographics alone. Members with the same demographics can cost very different amounts, so expensive members were under-priced, cheap ones over-priced, and the plans lost money. Over time the cheap members leave for competitors and the expensive ones stay, so the problem gets worse on its own.

## What I did

- Built a model that predicts each member's expected yearly claims cost from how they actually use care, not just from demographics.
- The business set prices on top of the predicted cost, with their own margins and limits on how much a premium can change at renewal.
- Checked that predicted costs add up to actual costs across the whole portfolio, which is what matters for pricing.

## Impact

- Pricing moved from flat rates per plan tier to risk-adjusted pricing per group.
- Groups priced with the model performed better than groups still on the old basis.
- The **Medical Expense Ratio came down** over the period. It also depends on claims experience and provider negotiations, so not all of the change is due to the model.

---

The work belongs to the company and is under NDA, so this page covers the problem, my role and the impact only.

[← Back to profile](../README.md)

