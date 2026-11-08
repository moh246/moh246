# Agentic Portfolio Analytics

Banking · LLM agents · RAG · text-to-SQL

## Problem

To answer a question about the portfolio, a corporate client or a customer form, bank staff had to call colleagues or search through paper records. That took a lot of time.

## What I built

Three separate chatbots, each built for a different kind of data. All of them run on Azure with GPT models.

### 1. Retail chatbot: agentic text-to-SQL

A LangGraph agent with one specialised tool per product: one for **Loans** and one for **Credit Cards**. Each tool has its own prompt and searches only its own table columns, so it doesn't mix the two up.

Around it:

- **Schema database:** describes the tables so the agent knows what it can query
- **Question → SQL engine:** turns a question into a query
- **Question → Plotly engine:** turns the answer into a chart
- **Tracing per component** with OpenTelemetry/Traceloop, so a bad answer can be traced back to the step that broke
- **LLM judge** that checks the final answer

When a generated query fails, the agent retries up to 5 times. If it still can't get it right, it says so plainly and suggests related questions it *can* answer, instead of guessing.

### 2. Corporate chatbot: RAG over documents

Answers questions about corporate clients and how the bank works with them, using standard RAG over a set of PDFs.

### 3. Know-your-customer chatbot: hybrid search

Covers know-your-customer material and customer onboarding forms. Users sometimes need a form returned exactly as it is, and sometimes one specific piece of information. So it combines RAG with keyword search.

## Result

| Chatbot | Users |
|---|---|
| Retail | 3,000+ |
| Corporate | about 2,500 |
| Know-your-customer | 500–1,000 |

- The LLM judge scored the answers **above 90%**.
- Staff now find the answer in the chatbot instead of calling people or searching paper records.

## Stack

LangGraph · GPT models on Azure · text-to-SQL · RAG · keyword search · Plotly · OpenTelemetry/Traceloop · LLM-as-judge

---

The code belongs to the company and is under NDA. This page describes the design only.

[← Back to profile](../README.md)
