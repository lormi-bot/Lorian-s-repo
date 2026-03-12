---
name: kpi-framework-builder
description: >
  This skill should be used when the user wants to build a KPI framework for a new domain.
  Combines data-possible KPIs from a data landscape scan with domain-important KPIs from
  domain research, producing a refined KPI framework with definitions and drivers, and an
  open research agenda of questions and benchmarks to investigate. Pauses for human review
  before the workflow continues.
user_invocable: true
compatibility:
  platforms:
    - claude-code
metadata:
  version: "1.0.0"
---

# KPI Framework Builder

Combine data-available KPIs and domain-important KPIs into a refined framework with definitions, drivers, and a research agenda.

## Workflow

1. **Gather inputs** — Collect the orientation summary from domain-skim, the initial KPI candidate list from data-landscape-scan (Variant A) or note that no dataset is available (Variant B), and the domain brief prompt.

2. **Build the domain KPI list** — Based on the orientation summary, identify the KPIs that domain experts and top-performing SaaS enterprise companies consider most important for this domain. For each KPI, note: name, definition, why it matters, what drives it.

3. **Merge with data-available KPIs (Variant A)** — Cross-reference the domain KPI list with the initial KPI candidate list from data-landscape-scan. Classify each KPI as:
   - Measurable now (column exists in dataset)
   - Measurable with calculation (columns exist but require formula)
   - Not measurable (column missing — flag as strategic gap)

4. **Identify strategic gaps** — For KPIs that are domain-important but not measurable, flag these explicitly as strategic gaps to surface to leadership. These are often the most valuable findings.

5. **Handle conflicting definitions** — If the same KPI has different definitions across sources, present both and ask the user to choose the preferred definition before proceeding.

6. **Draft research agenda** — Generate 5-7 open questions and investigation items that the deep research steps should answer. Each item should be specific and answerable (e.g., "What is the median pipeline coverage ratio for B2B SaaS enterprise companies above $50M ARR?"). Prioritise questions that will most influence the advice you give.

7. **Present for human review** — Present the KPI framework table and research agenda to the user. Ask them to confirm, adjust, or add items before the workflow continues. Do not proceed until the user explicitly approves.

## Outputs

### KPI Framework Table (presented to user for review)

| KPI | Definition | Why it matters | Key drivers | Measurability (Variant A) |
|-----|-----------|----------------|-------------|--------------------------|
| [name] | [definition] | [why] | [drivers] | Measurable / Needs calc / Gap |

### Research Agenda (presented to user for review)

Numbered list of 5-7 specific, answerable questions for the deep research phase.

### Strategic Gaps List

Explicit list of domain-important KPIs not measurable from available data, with a note on why each matters.

## Guidelines

- Always pause for human review before the workflow continues — this is a hard checkpoint
- Be specific about KPI definitions — vague KPIs produce vague models
- Flag conflicting definitions rather than picking one silently
- Keep the research agenda focused — 5-7 questions is enough; more creates unfocused research
- For Variant B (no dataset), skip measurability column and focus entirely on domain-important KPIs
