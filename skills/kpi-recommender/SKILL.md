---
name: kpi-recommender
description: >
  This skill should be used when the user wants to define which KPIs to include in a financial model.
  Takes a business question, available dataset variables, and domain — produces a prioritised KPI list
  with definitions, formula logic, benchmarks, and flags for missing data.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: model-build
  step: "4"
---

# KPI Recommender

Recommend and define the most relevant KPIs for a financial model based on the business question and available data.

## Workflow

1. **Gather inputs** — Collect from the user:
   - The business question the model needs to answer (one sentence)
   - The available variables in the dataset (column names or categories)
   - The business domain (SaaS metrics, Sales/Pipeline, P&L, ARR, Marketing, Operations, etc.)
   - Whether benchmarks or targets need to be included

2. **Generate KPI candidates** — Based on the business question and domain, generate a full list of candidate KPIs. Draw on:
   - Standard SaaS metrics (ARR, MRR, NRR, GRR, CAC, LTV, CAC Payback, Rule of 40, Magic Number, Burn Multiple, Pipeline Coverage, Win Rate, ACV, Churn Rate, Expansion Revenue, Logo Retention)
   - Domain-specific operational metrics relevant to the question
   - Leading indicators (forward-looking) as well as lagging indicators (backward-looking)
   - At least one metric that connects to PE sponsor / board priorities

3. **Prioritise** — Classify each KPI:
   - **Essential** — directly answers the business question; model cannot do its job without it
   - **Important** — adds significant analytical value; include if data is available
   - **Nice-to-have** — useful context; include if time allows

4. **Define each KPI** — For every Essential and Important KPI, provide:
   - Plain-English definition
   - Formula: numerator ÷ denominator (or sum/rate logic)
   - Time period (point-in-time, period, trailing 12M, etc.)
   - Benchmark or target range where available
   - Whether it requires Power Pivot (DAX) or can be calculated in Excel
   - Potential definition conflict: flag if the business might define this differently

5. **Flag missing data** — For KPIs that cannot be calculated from the available variables:
   - Name the KPI and its value
   - Identify the missing variable(s)
   - Suggest where the data might come from or how to approximate it

6. **Confirm** — Present the prioritised KPI list and ask: "Does this match how your business defines these metrics? Any KPIs you'd add or remove?"

## Outputs

KPI list is delivered in the conversation as a formatted table. No file saved unless requested.

Each KPI entry includes: Name | Priority | Definition | Formula | Time Period | Benchmark | Calculation Method | Notes

## Guidelines

- Always include at least one leading indicator alongside lagging metrics
- Always connect at least one KPI to the PE sponsor's value creation priorities
- Flag where industry-standard definitions may differ from company convention — never assume
- If the business question is too vague to recommend KPIs, ask for the specific decision the model will support before proceeding
- After confirming the list, suggest: "Before designing the model architecture, let's confirm these KPI definitions match how your finance team and exec team define them — inconsistency here is one of the most common causes of model disputes."
