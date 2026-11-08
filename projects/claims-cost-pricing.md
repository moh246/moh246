# Risk-Based Pricing for Health Insurance Plans

Health insurance · Pricing · Regression

## Problem

Corporate health plans were priced on demographics alone: age, location, employer location. But two members with identical demographics can differ several-fold in actual cost, depending on which providers they use and their history of using care. So expensive members were systematically under-priced and cheap ones over-priced, and the plans lost money overall.

Flat pricing also gets worse on its own. Cheap members leave for a competitor that prices them more accurately, expensive members stay because the price is attractive for them, and the risk pool degrades. That's adverse selection.

## What I built

- **A model of expected annual claims cost per member**, using provider usage, point of purchase and medical history, not just demographics.
- **XGBoost rather than a GLM.** GLMs are the industry standard for pricing because their coefficients map onto rating tables and are easy for a regulator to read. But here the signal was in interactions: provider choice interacts with condition, which interacts with location. A GLM only captures those if you specify each one by hand, while trees find them automatically. The trade-off is a weaker form of explanation (SHAP values instead of a rating table).
- **The model predicts cost, not price.** The business builds the price on top: loadings for expenses, margin and uncertainty, plus commercial caps on how far a premium can move at renewal.
- **Calibration at portfolio level as the key check.** Error per member matters less than whether the sum of predicted costs matches the sum of actual costs. A model can look accurate per member and still under-predict in total, and in pricing that's the failure that costs money.

## Result

Pricing moved from flat rates by plan tier to risk-adjusted pricing per group. The Medical Expense Ratio came down over the period, and the groups priced with the model performed better than the groups still on the old basis. The ratio also moves with claims experience and network negotiations, so not all of the change is down to the model.

## Stack

XGBoost · SHAP · Python

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
