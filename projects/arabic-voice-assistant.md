# Arabic Voice Assistant

Consulting · Insurance · Speech · Arabic

## Problem

A Saudi insurer processes tens of thousands of prescriptions a day. Its teams had a lot of questions about that data: who did a given transaction, when it happened, how many transactions came in per day. They wanted to ask those questions by voice, in Arabic, and get an answer back.

## What I built

A full voice pipeline built on open-source models and deployed to production:

- **Speech-to-text:** Whisper large turns the spoken Arabic question into text. It already handles Gulf Arabic well, and I fine-tuned it on about 40 hours of Modern Standard Arabic speech with transcripts from Hugging Face.
- **LLM:** Qwen turns that question into a SQL query and runs it against the prescriptions database. Prompting alone was enough here, with no fine-tuning.
- **Text-to-speech:** XTTS v2 reads the answer back. It didn't need fine-tuning.

I've also post-trained and deployed open-source models for a bank's retail business.

## Result

Deployed to production. A spoken question gets a spoken answer in **5–8 seconds**. So the wait doesn't feel long, the answer is streamed, and longer answers are split into parts when needed.

## Stack

Whisper large · Qwen · text-to-SQL · XTTS v2 · Arabic NLP

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
