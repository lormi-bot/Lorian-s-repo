---
name: library-writer
description: >
  This skill should be used when the user wants to write article summaries to
  the intelligence library. Receives a formatted summary block pasted from Agent
  36 (output of the Article Summarizer skill), reads the existing intelligence-library.md,
  and appends new summaries under the correct domain sections — maintaining file
  organization, session headers, and newest-first ordering. Creates the library
  file with full structure if it does not yet exist.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: Article Knowledge Capture — Step 5
  agent: Claude Code
---

# Library Writer

Append article summaries from a formatted export block into the intelligence library, organized by domain.

## Workflow

1. **Receive the export block** — The user pastes a formatted summary block produced by the Article Summarizer skill. The block contains a session header and domain-grouped summary cards. If no block is pasted, ask: "Please paste the summary block from Agent 36."

2. **Read the library file** — Read `07-intelligence-layer/36-news-magazine-reader/intelligence-library.md`.
   - File exists → proceed to Step 3
   - File does not exist → create it with the full structure below, then proceed to Step 3:

   ```markdown
   # Intelligence Library

   *Personal knowledge base — articles captured and summarized by Agent 36*
   *Last updated: [YYYY-MM-DD]*

   ---

   ## SaaS

   ## PE

   ## AI

   ## Leadership

   ## Macro
   ```

3. **Parse the export block** — Identify:
   - Session date and article count from the session header
   - Domain sections and the summary cards within each section

4. **Append summaries** — For each domain section in the export block:
   - Locate the matching domain section in `intelligence-library.md`
   - Insert the session header + summary cards at the top of that domain section (newest first)
   - Preserve all existing entries below

5. **Update the last-updated date** — Replace the `*Last updated: [date]*` line with today's date.

6. **Write the file** — Write the updated content back to `07-intelligence-layer/36-news-magazine-reader/intelligence-library.md`.

7. **Confirm** — Report to the user:
   - How many articles were written
   - Which domains were updated
   - The file path
   - Reminder: "Upload the updated `intelligence-library.md` to relevant agent Projects in Claude.ai when you want agents to be able to retrieve these articles."

## Outputs

### `07-intelligence-layer/36-news-magazine-reader/intelligence-library.md`

Growing personal knowledge base. Structure:
- File header with last-updated date
- Five domain sections: SaaS, PE, AI, Leadership, Macro
- Within each domain: sessions in reverse chronological order (newest first)
- Within each session: session header (`### Session: YYYY-MM-DD — N articles`) + summary cards

## Guidelines

- Always read the existing file before writing — never overwrite blindly
- Preserve all existing entries — only append, never delete or modify existing summaries
- Newest sessions appear first within each domain section
- If the pasted block contains a domain not in the taxonomy (SaaS / PE / AI / Leadership / Macro), flag it and ask Lorian to confirm before adding a new section
- If the block is incomplete or partially pasted, write what's available and note what appears to be missing
- File path is fixed: `07-intelligence-layer/36-news-magazine-reader/intelligence-library.md`
