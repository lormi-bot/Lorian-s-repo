---
name: publication-scanner
description: >
  This skill should be used when the user wants to scan a defined list of
  publications for recent articles relevant to their role. Searches each
  publication using web search, applies a relevance filter, and produces a
  curated table with title, publication, date, a specific "why it matters"
  field, and link. Designed for Agent 36 (News & Magazine Reader) in the
  CFO Operating System.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: Publication Intelligence Scan
  agent: Agent 36 — News & Magazine Reader
---

# Publication Scanner

Search a defined list of publications for recent relevant articles and deliver a curated table with a specific "why it matters" field for each article.

## Workflow

1. **Receive session parameters** — Check if the user has stated any adjustments to the default publication list, topic focus, or time window. If no adjustments, proceed with defaults. Default time window: past 7 days.

2. **Search each publication** — Use web search to find recent articles from each publication in the confirmed list. Apply the relevance filter:
   - CFO role development and career transition
   - PE-backed SaaS: business model, metrics, value creation, exit dynamics
   - AI in finance and technology: disruption, tools, new business models
   - Executive leadership and influence
   - Macro environment for tech: interest rates, enterprise spending, cloud optimisation
   - SaaS valuations, benchmarks, M&A and deal flow

3. **Apply inclusion rules** — For each article found:
   - Clearly relevant → include
   - Paywalled → include with available metadata; flag as [paywalled]
   - Borderline → include with a note on marginal relevance
   - Clearly irrelevant → exclude without flagging
   - If >15 results pass the filter → apply stricter filter; keep highest-relevance only
   - If <5 results → note the limitation; suggest broadening time window

4. **Write the "why it matters" field** — For each included article, write a specific relevance statement tied to the user's CFO transition, their company context, or their PE sponsor relationship. Generic statements are a quality failure. The test: if the user reads only this field, do they immediately understand why this article is worth their time?

5. **Assemble and deliver the table** — Present results ordered by relevance (most relevant first), target 8–15 articles. Note any publications that returned no usable results below the table.

6. **Wait for user response** — Three outcomes:
   - Accept → skill ends; output is the curated table
   - "Dig deeper on [topic]" → invoke Topic Deep Diver skill for that topic
   - "Re-run with [adjustment]" → return to Step 1 with revised parameters

## Outputs

### Curated Article Table

| # | Title | Publication | Date | Why it matters for you | Link |
|---|-------|------------|------|----------------------|------|

Delivered in the conversation. 8–15 articles, ordered by relevance. Publications returning no results noted below the table.

## Guidelines

- "Why it matters for you" must be specific — never generic. Frame as: how does this help the user be a better CFO or understand the world their company operates in?
- Paywalled articles are included and flagged — the title and relevance may be enough; the user can decide whether to access it
- If web search is unavailable, inform the user and ask them to paste article titles/links manually
- Do not include articles older than the stated time window unless the user requests historical coverage
- The scan is only as good as the relevance judgment — when in doubt about inclusion, include with a note rather than exclude silently
