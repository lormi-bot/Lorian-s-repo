---
name: topic-deep-diver
description: >
  This skill should be used when the user wants to go deeper on a specific
  topic surfaced during an intelligence scan. Searches broadly across all
  sources (not limited to a default publication list), produces a structured
  mini-brief covering what is happening, why it matters, key debates, and the
  company implication — followed by 3-5 additional articles on the same and
  adjacent topics.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: Publication Intelligence Scan — Step 5
  agent: Agent 36 — News & Magazine Reader
---

# Topic Deep Diver

Produce a focused mini-brief on a named topic plus additional articles on the same and adjacent topics.

## Workflow

1. **Identify the topic** — Take the topic name from the user's instruction (e.g. "dig deeper on AI in SaaS pricing"). If the topic is broad (e.g. "AI"), ask the user to narrow it before searching: "AI in finance? AI in SaaS pricing? AI disruption risk for enterprise software?"

2. **Search broadly** — Use web search to find the most current and authoritative content on this topic. Do not limit to the default publication list — search across all relevant sources including academic papers, analyst reports, Substack authors, and specialist publications.

3. **Write the mini-brief** — Produce a structured summary in this exact format:

```
TOPIC: [Topic name]
WHAT IS HAPPENING: [2-3 sentences — current state of play, most recent developments]
WHY IT MATTERS FOR YOU: [Specific to the user's CFO transition and company context]
KEY POSITIONS/DEBATES: [What informed people in this space disagree about — the live intellectual tension]
ARIA IMPLICATION: [What this means specifically for a PE-backed SaaS company at the user's stage]
```

4. **Surface additional articles** — Find 3–5 additional articles on the same and adjacent topics. Present in the same table format as the main scan:

| # | Title | Publication | Date | Why it matters for you | Link |
|---|-------|------------|------|----------------------|------|

5. **Return to review** — After delivering the mini-brief and additional articles, return control to the user. They can: accept, request another dig deeper on a different topic, or re-run the main scan.

## Outputs

### Mini-Brief

Structured summary: Topic, What is Happening, Why it Matters, Key Debates, Company Implication.

### Additional Articles Table

3–5 articles in the standard scan table format, on same and adjacent topics.

## Guidelines

- Search broadly — the value of this skill is going beyond the default publication list to find the best available content on the specific topic
- "Why it matters for you" and "Aria Implication" must be specific — not generic observations about the topic
- "Key Positions/Debates" is the most valuable field — identify the genuine intellectual tension, not just a summary of the article
- If the topic is too niche and few articles exist, flag this honestly and offer the best available
- If no new articles exist beyond what appeared in the main scan, say so and offer the mini-brief only
- Handle multiple topics sequentially — complete one mini-brief before moving to the next; ask for priority if more than two topics are flagged
