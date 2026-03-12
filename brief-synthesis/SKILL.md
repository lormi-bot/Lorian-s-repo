---
name: brief-synthesis
description: >
  This skill should be used when the user wants to synthesise all domain research outputs
  into a complete Domain Intelligence Brief. Produces an 8-layer public brief with quality
  index ratings per layer, a private annotations template, and saves both as versioned
  markdown files. Uses Claude Opus for best output quality on this demanding synthesis step.
user_invocable: true
compatibility:
  platforms:
    - claude-code
metadata:
  version: "1.0.0"
---

# Brief Synthesis

Consolidate all research outputs into a complete, versioned Domain Intelligence Brief with quality index ratings and two-layer structure.

## Workflow

1. **Gather all inputs** — Collect: orientation summary (domain-skim), KPI framework (kpi-framework-builder), domain landscape map, benchmark database, best practice library, failure pattern list (deep-research), PDF source list with file paths, and stakeholder profile from the domain brief prompt.

2. **Determine filename** — Construct the brief filename using the naming convention: `briefs/[domain-slug]-v1-[YYYY-MM].md`. Derive the domain slug from the domain name (lowercase, hyphens, descriptive — e.g., `pipeline-management`, `competitive-strategy`).

3. **Synthesise each layer** — Write the 8 layers in order. For each layer, apply the quality index and assign an overall confidence signal:

   **Layer 1 — Orientation**
   Key concepts, definitions, and mental models. Write for someone encountering this domain for the first time. Each concept should be defined clearly and connected to adjacent concepts.

   **Layer 2 — KPI Framework**
   The KPI framework from kpi-framework-builder, enriched with benchmark data from deep-research. For each KPI: name, definition, why it matters, key drivers, and benchmark (good / great / superb) with confidence signal.

   **Layer 3 — Lever Map**
   The main levers for value creation in this domain and how they connect. Show the hierarchy: which levers are primary (direct impact), which are secondary (enable primary levers), and which are foundational (required but not differentiating).

   **Layer 4 — Failure Modes & Traps**
   Common mistakes, misconceptions, and what separates average from excellent practitioners. Be specific — name the trap and describe exactly what it looks like in practice.

   **Layer 5 — Expert Frameworks**
   The top frameworks and methodologies used by domain leaders. For each: name, origin, what it explains, how to apply it, and quality index rating.

   **Layer 6 — Diagnostics Toolkit**
   The questions an expert asks to rapidly assess the health of this domain area. Organise by diagnostic category. These should be questions you can ask in a meeting to immediately signal credibility.

   **Layer 7 — Learning Roadmap**
   A sequenced 4-8 week plan to reach leadership-level knowledge. Week-by-week: what to read, what to practice, what conversations to have, and what you should be able to do at the end of each phase.

   **Layer 8 — Surgical Reading List**
   From the user's PDF library: specific books, chapters, pages, and paragraphs. For each entry: file path, page/section reference, and a one-sentence note on exactly what insight or framework it contributes and why it matters for this domain.

4. **Apply quality index per layer** — End each layer with:
   ```
   Quality: Durability [Stable/Evolving/Volatile] | Authority [Research-backed/Practitioner/Opinion] | Consensus [Consensus/Debated/Contested] | Relevance [High/Medium/Low] → Overall: 🟢/🟡/🔴
   ```

5. **Handle conflicts and gaps** — If sources conflict on a point, present both views and flag for the user. If a layer is thin due to insufficient research, mark it 🔴 with an explicit note: "Limited sources found — validate before using."

6. **Check for revision needs** — During synthesis, if any finding appears to contradict validated knowledge or require a change to something previously confirmed, ask the user before including it.

7. **Write the public brief** — Save to `briefs/[domain-slug]-v1-[YYYY-MM].md`. The public brief contains only AI-generated, source-backed content. No company-specific data, internal benchmarks, or proprietary information.

8. **Write the private annotations template** — Save to `briefs/[domain-slug]-private-annotations.md`. This file stays local only — never upload it to Claude Projects or any AI tool. Pre-populate with prompts for the user to fill in:
   - Company-specific benchmarks for each KPI in Layer 2
   - Internal methodology notes for Layer 5
   - Org-specific context relevant to Layer 3 (lever map)
   - Stakeholder-specific diagnostics to add to Layer 6

9. **Confirm output** — Tell the user both files have been saved and remind them that the private annotations file should never be uploaded to Claude Projects.

## Outputs

### `briefs/[domain-slug]-v1-[YYYY-MM].md` — Public Domain Intelligence Brief

8-layer brief with quality index per layer. Safe to use in any AI tool.

### `briefs/[domain-slug]-private-annotations.md` — Private Annotations Template

Pre-populated template for company-specific context. Local only — never uploaded.

## Guidelines

- This is the most demanding synthesis step — take depth over speed
- Every layer must have a quality index rating — no exceptions
- Never include company-specific information in the public brief
- Layer 8 must have specific page/paragraph references, not just book titles — if citations are thin, flag to user
- If synthesising across conflicting sources, always present both and let the user decide
- Keep each layer focused — aim for depth on what matters, not exhaustive coverage of everything
- Remind the user at the end: the brief is a living document — it improves with each domain engagement
