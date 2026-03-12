---
name: data-landscape-scan
description: >
  This skill should be used when the user has a dataset available and wants to map what
  KPIs are measurable from it. Reads an Excel export from the data warehouse, scans column
  names to identify available variables, drafts an initial KPI candidate list, and sketches
  a visual dashboard concept. Used as Variant A input to kpi-framework-builder.
user_invocable: true
compatibility:
  platforms:
    - claude-code
metadata:
  version: "1.0.0"
---

# Data Landscape Scan

Read an Excel export from the data warehouse, map available variables to KPI candidates, and sketch a dashboard concept.

## Workflow

1. **Get the file path** — Ask the user for the path to the Excel export from their data warehouse. If the path is not provided, prompt: "What is the file path to your data export? (e.g., E:\OneDrive\Data\pipeline-export.xlsx)"

2. **Read the file** — Read the Excel file. Focus on column names across all sheets. Note: the number of rows, sheet names, and any immediately visible data quality issues (blank columns, inconsistent naming, etc.).

3. **Map columns to KPI candidates** — For each column, consider: what KPI or metric could this variable contribute to? Group related columns (e.g., `deal_value` + `deal_stage` + `close_date` → Pipeline Coverage, Win Rate, Average Deal Size). Produce an initial KPI candidate list.

4. **Flag cryptic column names** — If column names are ambiguous or use internal codes (e.g., `fld_003`, `acct_typ_cd`), flag them and ask the user to clarify before including them in the KPI list.

5. **Identify data quality issues** — Note any visible issues: large numbers of blank values, inconsistent formatting, potential duplicates, date range of the data. These are investigation items for the research agenda.

6. **Sketch dashboard concept** — Based on the KPI candidates, sketch a visual dashboard concept: which KPIs belong together, what chart type suits each (trend line, bar chart, funnel, scatter plot), and what narrative the dashboard would tell. This is a hypothesis — it will be refined after domain research.

7. **Identify strategic gaps** — Which domain-important KPIs are likely missing from this dataset? Based on the domain name, flag the most common KPIs for this domain that are not represented in the columns. These become the most important items on the research agenda.

8. **Produce output summary** — Present the KPI candidate list, dashboard concept sketch, data quality flags, and strategic gaps. Pass this output to kpi-framework-builder.

## Outputs

### KPI Candidate List

Table of KPI candidates with: KPI name, contributing columns, calculation approach (if known), data quality notes.

### Dashboard Concept Sketch

Narrative description of: KPI groupings, suggested chart types per KPI, the story the dashboard would tell.

### Strategic Gaps List

Preliminary list of domain-important KPIs likely absent from the dataset.

### Data Quality Flags

List of data issues to investigate further.

## Guidelines

- Always flag cryptic column names rather than guessing their meaning
- The dashboard concept is a hypothesis — keep it light, it will be refined
- Strategic gaps are often the most valuable output — common missing KPIs signal important conversations to have with leadership
- Do not attempt to calculate any KPIs at this stage — this is a mapping step only
- If the Excel file has multiple sheets, scan all sheets before producing the KPI list
