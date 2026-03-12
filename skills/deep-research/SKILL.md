---
name: deep-research
description: >
  This skill should be used when the user wants to perform structured deep research on a
  domain in two phases: Lay of the Land (mapping the domain fully) and Benchmarking (what
  good, great, and superb looks like). Applies a four-dimension quality index to every
  source and finding. Produces a domain landscape map, benchmark database, best practice
  library, and failure pattern list.
user_invocable: true
compatibility:
  platforms:
    - claude-code
metadata:
  version: "1.0.0"
---

# Deep Research

Perform structured domain research in two parallel phases — Lay of the Land and Benchmarking — with quality index scoring on every finding.

## Workflow

### Phase 1 — Lay of the Land

1. **Load inputs** — Read the research agenda from kpi-framework-builder and the orientation summary from domain-skim. Use the research agenda to focus the research.

2. **Research domain structure** — Run targeted web searches to map the domain fully: key components and how they fit together, typical processes and methodologies, stakeholder roles and org structures, domain-specific terminology. Focus on SaaS enterprise context throughout.

3. **Deep-read PDFs** — Return to the PDFs identified in domain-skim and read the sections most relevant to the research agenda. Extract specific frameworks, models, and practitioner insights. Note file paths and page locations for Layer 8 citations.

4. **Handle sub-areas** — If the domain has significant sub-areas, prioritise the sub-areas most relevant to the business context from the domain brief prompt. Note other sub-areas briefly.

5. **Produce landscape map** — Summarise: key components and their relationships, common processes and methodologies, typical stakeholder roles, essential terminology.

### Phase 2 — Benchmarking

6. **Research KPI benchmarks** — For each KPI in the approved KPI framework, search for benchmark data: what does the top quartile look like for SaaS enterprise companies? Segment benchmarks by relevant peer group (ARR range, company stage, go-to-market model) where data is available.

7. **Research best practices** — Identify the specific initiatives, programmes, and practices that top-performing SaaS enterprise companies use in this domain. Be concrete: not "they have better processes" but "they use X methodology / Y framework / Z approach."

8. **Research failure patterns** — What do average or underperforming companies do differently? What are the common mistakes, misconceptions, and traps?

9. **Apply quality index to every finding** — For each significant finding, benchmark, or best practice, assign:

   | Dimension | Rating options |
   |-----------|---------------|
   | **Durability** | Stable (foundational, timeless) / Evolving (improving understanding) / Volatile (changes frequently) |
   | **Authority** | Research-backed (data/studies) / Practitioner (real-world experience) / Opinion (single perspective) |
   | **Consensus** | Consensus (widely agreed) / Debated (mixed views) / Contested (significant disagreement) |
   | **Relevance** | High (SaaS enterprise specific) / Medium (general SaaS) / Low (generic business) |

   **Overall confidence:** 🟢 High (3-4 dimensions strong) / 🟡 Medium (mixed) / 🔴 Low (weak sourcing or contested)

10. **Flag notable events** — If research surfaces a recent major development (new regulation, market disruption, landmark research paper) that might affect the domain, flag it as a potential edge case and ask the user whether it warrants special treatment in the brief.

11. **Flag sourcing gaps** — If a benchmark or best practice cannot be found for an important KPI or domain area, flag it explicitly with 🔴 confidence and note what proxy information was used instead.

## Outputs

### Domain Landscape Map

Structured summary: components, processes, roles, terminology — all with quality index ratings.

### Benchmark Database

Per KPI: good / great / superb thresholds, peer group segmentation, source, quality index rating.

### Best Practice Library

Specific, named practices from top-performing SaaS enterprise companies, each with quality index rating.

### Failure Pattern List

Common mistakes and what separates average from excellent, each with quality index rating.

## Guidelines

- Always segment benchmarks by company stage/ARR — generic benchmarks are often misleading
- Never present a benchmark without a quality index rating — confidence signals are non-negotiable
- Prefer recent sources (within 2 years) for Volatile elements; Stable principles can come from older authoritative sources
- If a major external event is found during research, always ask the user before treating it as an edge case — do not silently include it
- Flag every sourcing gap rather than filling it with low-quality data
