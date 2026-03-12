---
name: visual-advisor
description: >
  This skill should be used when the user wants advice on how to visualise a financial metric or dataset.
  Takes a metric, the insight to communicate, and the audience — produces a chart type recommendation,
  design brief, conditional formatting approach, and latest technique guidance for Excel or Power BI.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: model-build
  step: "8"
---

# Visual Advisor

Recommend chart types, dashboard layout, and design approach for communicating financial insights to executives.

## Workflow

1. **Gather inputs** — Collect from the user:
   - The metric or KPI to visualise
   - The insight to communicate: what do you want this visual to make obvious?
   - The audience (exec team, operational team, self-use)
   - The tool: Excel or Power BI
   - Whether benchmarks, targets, or prior period comparisons need to be shown
   - Whether this is a standalone chart or part of a broader dashboard

2. **Recommend the chart type** — Based on what the visual needs to communicate:

   | Purpose | Recommended chart |
   |---------|------------------|
   | Trend over time | Line chart (single metric) or combo line+bar (metric + comparison) |
   | Period-over-period comparison | Clustered bar or column |
   | Composition / breakdown | Stacked bar (avoid pie charts for exec audiences) |
   | Variance from budget/target | Waterfall chart |
   | Two-variable relationship | Scatter plot |
   | Many metrics at a glance | KPI card grid |
   | Distribution | Histogram or box plot |
   | Part of a whole over time | Area chart (use sparingly) |
   | Rankings | Horizontal bar sorted descending |
   | Small multiples / by segment | Faceted bar or line charts |

   Explain why this chart type was chosen and what alternatives were rejected.

3. **Design the visual** — Provide specific design guidance:
   - Chart title: should state the insight, not just the metric name (e.g. "Pipeline Coverage Below 3x Target" not "Pipeline Coverage")
   - Axis labels: minimal, clear, no unnecessary gridlines
   - Colour palette: use 1-2 accent colours maximum; use colour only to communicate meaning (e.g. red = below target, green = above)
   - Benchmark/target line: how to add a reference line in Excel or Power BI
   - Conditional formatting: how to implement above/below benchmark colour logic (including helper column approach for Excel)
   - Data labels: when to show, when to hide, how to format
   - Legend: position and whether it's needed

4. **Latest technique recommendation** — Flag:
   - Modern approaches that replace outdated ones (e.g. "avoid 3D charts, avoid pie charts with >4 segments, avoid rainbow colour schemes")
   - Excel-specific modern techniques (dynamic chart titles using cell references, sparklines for trend indicators, conditional formatting on chart markers)
   - Power BI-specific techniques (conditional column colours, smart narrative, KPI visual, bookmark navigation)

5. **Helper column requirements** — If conditional colour logic requires supporting data (e.g. separate columns for "above benchmark" and "below benchmark" values), specify exactly what helper columns are needed and how to structure them.

6. **Dashboard layout** (if part of a broader dashboard) — Advise on:
   - Where this visual sits relative to others (most important = top left)
   - White space and visual grouping
   - How many charts per dashboard page (exec: max 6-8)
   - Navigation if multi-page

## Outputs

Visual design brief is delivered in the conversation. No file saved unless requested.

Each response includes:
- Chart type recommendation with rationale
- Specific design brief (title, colours, labels, benchmark line)
- Helper column requirements (if needed)
- Latest technique note
- Step-by-step build guidance for the specific chart type in Excel or Power BI

## Guidelines

- Always ask "what do you want this visual to make obvious?" before recommending a chart type — the insight drives the design, not the data shape
- Executive dashboards: fewer charts, larger text, insight-led titles, clear call-to-action
- Avoid: 3D charts, pie charts with >4 segments, rainbow colour schemes, chart junk (unnecessary gridlines, borders, shadows)
- Every visual must link to live calculations — flag if the user is considering hardcoded values
- After delivering the design brief, ask: "Would you like me to walk through how to build this step by step in Excel/Power BI?"
- Proactively suggest: "Before building 10 visuals, build one, show it to a colleague, and get their reaction — iterate fast before scaling"
