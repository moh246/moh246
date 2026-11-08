# Net Promoter Score Program and Member Feedback Classification

Health insurance · Product management · NLP

## Problem

The company ran a Net Promoter Score survey, but the free-text answers ("why did you give this score?") were hard to act on at volume. Someone had to read them to find out what was actually wrong.

## What I did

- **Product management (volunteer).** Alongside my data science role, I took on the product management of the Net Promoter Score project to learn how a product gets built end to end, from requirements through to delivery.
- **A classifier for member feedback.** Free-text comments were mapped into a two-level taxonomy (8 categories and 24 subcategories) with zero-shot classification, so no labelled data was needed:
  - It uses a model trained on natural language inference (BART-MNLI). The comment is the premise, and a sentence like "This text is about claim delays" is the hypothesis.
  - High entailment means the label applies. Running every candidate label and taking the strongest gives a classifier built from a list of category names alone.
- **Categories from the business, not from me.** The labels used the business's own wording, which also made the output easy for them to read.
- **Evaluation on a hand-labelled sample.** Zero-shot skips the training set, but it doesn't skip the gold set.

I later used the same idea, zero-shot classification into a taxonomy defined by the business, at much larger scale for the [Voice of the Customer Reclassification](voc-reclassification.md).

## Result

Member feedback became categories the teams could act on, instead of free text nobody had time to read.

## Stack

Zero-shot classification · BART-MNLI · Python

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
