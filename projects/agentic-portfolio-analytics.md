# Agentic Portfolio Analytics

Banking · LLM agents · text-to-SQL

## Problem

Teams needed answers from portfolio data without writing SQL themselves.

<!-- TODO: check this problem line and add specifics (who uses it, what they did before). -->

## What I built

An enterprise system with three chatbots: **Retail**, **CIOC** and **Corporate**.

The Retail bot is a LangGraph SQL agent over the Loans and Credit Cards data. It's made of separate parts, so each one can be tested and traced on its own:

- **Schema database:** describes the tables so the agent knows what it can query
- **Prompting** layer
- **Question → SQL engine:** turns a question into a query
- **Question → Plotly engine:** turns the answer into a chart
- **Tracing per component** with OpenTelemetry/Traceloop, so a bad answer can be traced back to the step that broke
- **LLM judge** that checks the final answer

When a generated query fails, the agent retries up to 5 times. If it still can't get it right, it says so plainly and suggests related questions it *can* answer, instead of guessing.

## Result

<!-- TODO: add a result you can share, e.g. number of users, questions answered, LLM-judge pass rate, time saved per request. -->

The Retail bot answers questions on loans and credit cards and draws charts from the results. When it can't answer, it says so and suggests related questions.

## Stack

LangGraph · text-to-SQL · Plotly · OpenTelemetry/Traceloop · LLM-as-judge

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
