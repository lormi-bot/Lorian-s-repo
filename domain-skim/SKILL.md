---
name: domain-skim
description: >
  This skill should be used when the user wants to build initial orientation on a new domain
  by searching their local PDF library and performing light web research. Searches OneDrive
  for relevant PDFs by filename and folder, reads the most relevant ones, runs a light web
  search, and produces an initial orientation summary covering key concepts, main drivers,
  and how they connect.
user_invocable: true
compatibility:
  platforms:
    - claude-code
metadata:
  version: "1.0.0"
---

# Domain Skim

Search the user's PDF library and perform light web research to build an initial orientation on a new domain.

## Workflow

1. **Read the domain brief prompt** — Extract the domain name, business context, and any specific questions from `context/domain-brief-prompt.md`. If the file does not exist, ask the user to describe the domain and context before proceeding.

2. **Search the PDF library** — Use Glob to search `E:\OneDrive\` recursively for PDF files whose filename or parent folder name contains keywords related to the domain. Generate 3-5 keyword variants (e.g., for "pipeline management": pipeline, revenue, sales, CRM, funnel). Present the matched file list to the user and ask them to confirm which are relevant before reading. If a filename is ambiguous (e.g., `module3-final.pdf`), ask the user to confirm relevance.

3. **Handle no-match case** — If no relevant PDFs are found, inform the user, note the gap, and proceed to web research only. Flag this in the output summary.

4. **Read confirmed PDFs** — Read each confirmed PDF. For each: extract key concepts, definitions, frameworks, and mental models relevant to the domain. Note the specific file path and approximate location of each key insight for Layer 8 of the brief.

5. **Run light web research** — Run 2-3 targeted web searches to orient on the current state of the domain: its key components, how practitioners talk about it, and what has changed recently. Focus on SaaS enterprise context.

6. **Produce orientation summary** — Write a structured summary covering:
   - Key concepts and definitions (what this domain is and how practitioners define it)
   - Main drivers (the factors that most influence outcomes in this domain)
   - Driver connections (how the main drivers relate to each other)
   - Most relevant PDFs found and read (file paths, key insight locations)
   - Preliminary driver map (simple hierarchy or diagram in text form)

7. **Flag domain characteristics** — Note: Is the domain highly specialised (prioritise practitioner sources)? Is it rapidly evolving (flag recency concerns)? Are there significant sub-areas that need scoping?

## Outputs

### Orientation Summary (in conversation)

Structured summary with: key concepts, main drivers, driver connections, PDF sources with file paths, preliminary driver map, and any flags.

### PDF Source List

A bulleted list of every PDF read, with file path and one-sentence note on what it contributed.

## Guidelines

- Always confirm PDF relevance with the user before reading — never assume
- If a domain has multiple sub-areas, ask the user which sub-area to prioritise before researching
- Prefer practitioner and analyst sources over generic content for SaaS enterprise context
- Keep the orientation summary focused — this is a foundation layer, not the full brief
- Note file paths precisely so Layer 8 of the brief can cite specific pages later
