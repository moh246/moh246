# Voice of the Customer Reclassification

Banking · Arabic NLP · I led this project

## Problem

Complaints from the mobile app kept landing in an "Other" bucket. Nobody owned that bucket, so the complaints never reached the team that could fix them.

## What I built

- **Labels defined with the business.** We ran a business study with the business teams and a business translator to define the labels: about 12 main categories, each with about 10 subcategories.
- **Zero-shot classification with BGE-M3.** No labelled training data needed. Each complaint is embedded with BGE-M3 and matched by similarity to the labels: first the main category, then the subcategory inside it. That's enough detail to route it to the right team. We ran it on more than 50,000 complaints. There's no vector database and no retrieval step. I chose BGE-M3 because it handles long texts, gives sparse and dense output, and copes with Egyptian colloquial Arabic, which is how customers actually write.

The results fed a Tableau dashboard, built by the data visualization team. It went through three versions and ended as a financial impact report for C-level: a four-tier churn model, a revenue waterfall, and methodology notes that keep transaction volume separate from bank revenue.

## Result

Classification accuracy went from about **60%** with the old regex rules to **92%**.

How we measured it:

1. Labelled a sample together with the business.
2. Built an **LLM labeller** that follows the same business rules, ran it on about 20,000 rows, and checked with the business that its labels were right.
3. Ran all 50,000+ complaints through the pipeline and compared its labels with the LLM labeller's.

Once the complaints reached the right teams, the issues behind them got fixed. That kept about half of a customer group worth over EGP 25M in profit: **roughly EGP 12M retained**.

## Stack

BGE-M3 · zero-shot classification · LLM-as-labeller for evaluation · Arabic NLP (Egyptian colloquial)

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
