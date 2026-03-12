---
name: article-summarizer
description: >
  This skill should be used when the user wants to summarize one or more articles
  from an intelligence scan or a provided link. Fetches each article via web search,
  produces a structured 8-field summary card (Core Argument, Key Insights, CFO
  Relevance, Aria Implication, Quote to Use, Save To domain), and formats all
  summaries as a clean export block organized by domain — ready to copy and write
  to the intelligence library.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: Article Knowledge Capture — Steps 2–4
  agent: Agent 36 — News & Magazine Reader
---

# Article Summarizer

Fetch selected articles, produce structured 8-field summary cards, and format as a clean export block organized by domain.

## Workflow

1. **Identify articles to process** — Determine the input type:
   - Article numbers (e.g., "summarize 2, 4, 7") → reference the scan table in the current conversation to retrieve titles and links
   - Article URL(s) → use the provided links directly
   - Pasted text → use the provided content directly; skip the fetch step

2. **Fetch each article** — For each article, use web search to retrieve the full article text via the link. Process articles sequentially.
   - Full text retrieved → proceed to Step 3
   - Paywalled / partial content only → flag as `[PAYWALLED]`, stop, and ask: "This article is paywalled — can you paste the text? (PDFs are available via your Telegram channels.)" Wait for paste before continuing.
   - Link broken or no result → flag and ask for an alternative link or pasted text

3. **Produce structured summary card** — For each article, write the 8-field summary card in this exact format:

   ```
   TITLE: [Article title]
   PUBLICATION: [Source] | DATE: [Date]
   CORE ARGUMENT: [1-2 sentences — what the article claims or argues]
   KEY INSIGHTS:
   - [Insight 1 — a specific, extractable idea]
   - [Insight 2]
   - [Insight 3]
   CFO RELEVANCE: [Specific to Lorian's CFO transition, goals, or stakeholder relationships — never generic]
   ARIA IMPLICATION: [What this means specifically for a PE-backed SaaS at Aria's stage — never generic]
   QUOTE TO USE: [The single most citable sentence — precise enough to use in a board conversation]
   SAVE TO: [SaaS / PE / AI / Leadership / Macro]
   ```

   Quality rules:
   - CFO Relevance and Aria Implication must be specific. Test: if Lorian reads only that field, does he immediately understand why this matters? Generic = quality failure.
   - KEY INSIGHTS are extractable ideas, not descriptions of what the article covers
   - QUOTE TO USE must be a verbatim or near-verbatim sentence from the article — precise enough to cite
   - SAVE TO: assign primary domain. If clearly multi-domain, note secondary in brackets

4. **Format export block** — After completing all summary cards, group them by domain and present as a single formatted block:

   ```
   ---
   ## Session: [YYYY-MM-DD] — [N] articles captured

   ### SaaS
   [Summary cards assigned to SaaS]

   ### PE
   [Summary cards assigned to PE]

   ### AI
   [Summary cards assigned to AI]

   ### Leadership
   [Summary cards assigned to Leadership]

   ### Macro
   [Summary cards assigned to Macro]
   ---
   ```

   Only include domain sections that have at least one article. Present the block with a clear instruction: "Copy the block above and paste it into Claude Code with `/library-writer` to write it to your intelligence library."

5. **Return control** — After delivering the export block, wait for Lorian's response. Options:
   - Lorian copies the block → workflow complete; Lorian proceeds to Claude Code for Step 5
   - "Summarize [more articles]" → repeat from Step 1 for the new selection; append to the same session block
   - "Re-do [article number]" → regenerate that summary card and update the export block

## Outputs

### Formatted export block

Presented in conversation. All summary cards grouped by domain under a session header. Ready to copy and paste to Claude Code for library write.

## Guidelines

- Process articles one at a time — complete each summary before moving to the next
- Never summarize from a scan table description alone — always fetch or use provided text
- Paywalled articles: flag immediately, do not attempt to summarize from abstract only
- If article content is thin (short piece, limited substance): complete summary with available content; note brevity in KEY INSIGHTS
- Domain taxonomy: SaaS / PE / AI / Leadership / Macro — these five only; no new domains without user confirmation
- Omit domain sections with no articles from the export block — do not include empty headers
- The export block is the deliverable — format it for clean copy, not for reading in the conversation
