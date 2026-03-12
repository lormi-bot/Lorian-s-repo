---
name: deck-builder
description: >
  This skill should be used when the user wants to design the slide skeleton for
  an executive presentation, write decision-oriented headlines and content briefs
  for each slide, and stress-test the finished deck from the exec's perspective.
  Takes the value creation narrative and recommendation package — produces a
  slide-by-slide skeleton with headlines, content types, and a stress-test verdict
  ready for Lorian to build in PowerPoint.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: exec-presentation-builder
  step: "2, 3, 4"
---

# Deck Builder

Design the slide skeleton, write decision-oriented headlines and content briefs, and stress-test the deck from the exec's perspective — all before PowerPoint is opened.

> **v1 — Baseline.** Upgrade when Executive Buy-in Presentation System course PDF arrives (29 March 2026).

## The Standard

A slide skeleton is ready when it tells the value creation story end-to-end — even without any content in the slides yet. Every slide has a clear reason to exist and a clear structural role in the argument.

A finished deck is ready when a sceptical exec, reading it cold, knows what decision they are being asked to make and feels equipped and motivated to make it.

## Important: PowerPoint Build

Lorian builds the actual slides in PowerPoint manually — data is confidential and cannot be shared with AI. This skill produces the content brief (headlines, bullet points, visual descriptions); Lorian transfers it to slides.

## Workflow — Step 2: Slide Skeleton

1. **Gather inputs** — Value creation narrative from Step 1; recommendation package from WF3 (including objection map); exec profile (time available, preferences); validated insights from WF2.

2. **Apply the AVSPS structure** — Map the narrative to slides:

   | Section | Role | Slide count guidance |
   |---------|------|---------------------|
   | **A — Action** | The ask — what decision is being made today | 1 slide (sometimes 2 if context-setting is needed) |
   | **V — Value** | Why this matters — what value creation is at stake | 1-2 slides |
   | **S — Safety** | Reduce cost of acting — address risks and concerns | 1-2 slides |
   | **P — Proof** | Evidence that justifies the recommendation | 2-4 slides |
   | **N — Next Step** | Who does what by when | 1 slide |

   Total target: 6-10 slides for a decision meeting. Never more than 12.

3. **Design each slide** — For every slide in the skeleton, define:
   - **AVSPS role:** Which section does this serve?
   - **Headline (draft):** The one point this slide makes — argumentative, not descriptive
   - **Content type:** Data visual / table / text / framework diagram / quote
   - **Narrative link:** Which part of the value creation narrative does this serve?
   - **Cut test:** If this slide were removed, would the argument break? If no, cut it.

4. **Headline principles** — The headline is the most important text on any slide:
   - States the conclusion, not the topic: "Pipeline Coverage Threatens Q4 ARR" not "Pipeline Coverage"
   - One sentence, past or present tense: "Win Rate Declined 8 Points in Q3" not "Win Rate Analysis"
   - Specific: "£2.1m ARR at Risk if Pipeline Gap Persists" not "ARR Risk"
   - If someone read only the headlines, would they understand the argument? → The "headline test"

5. **Skeleton coherence check** — Before proceeding to content:
   - Does the skeleton tell the story without any slide content?
   - Is the Action section first? (Never open with context or agenda)
   - Is the Safety section present before Proof?
   - Does one slide set up the next — is there a logical flow?

## Workflow — Step 3: Populate Content

6. **Write the content brief** — For each slide in the skeleton:
   - **Headline (final):** Refined from the skeleton draft
   - **Supporting content:** 2-3 bullet points OR a visual description (never both — choose one)
   - **Data reference:** Which specific metric, finding, or quote from WF2/WF3 supports this slide
   - **Visual brief (if applicable):** Chart type, what it shows, what the headline and the visual together must communicate — reference the visual-design-reference.md for chart type selection
   - **Talking point:** One sentence Lorian says out loud as this slide appears — not on the slide itself

   **Text density rules:**
   - Maximum 3 bullet points per slide
   - Each bullet point: 1 line, present or past tense, active voice
   - If a slide needs more than 3 bullets to make its point, it is trying to do too much — split or simplify
   - No paragraphs on slides — slides support the spoken narrative, not replace it

7. **Safety section design** — The Safety section is where most decks are underprepared:
   - This section directly addresses the objections from the WF3 objection map
   - For each major anticipated objection, one Safety slide that pre-empts it: "The main concern about [recommendation] is [X]. Here is how we have addressed that."
   - Safety slides reduce resistance before it is raised — they signal that Lorian has thought like an exec, not just like a finance professional

## Workflow — Step 4: Stress-Test

8. **Read the deck as the exec** — Apply the cold-read test: read the deck as a sceptical exec who has 15 minutes and limited patience:

   **Mandatory checks:**
   - Is the ask clear within the first 2 slides?
   - Does the Value section quantify what is at stake?
   - Is there a Safety section? Does it address the most likely resistance?
   - Is the Proof section after the ask (not before)?
   - Is the Next Step specific — named owner, action, date?

   **Logic gap check:**
   - Is there any slide that makes a claim without evidence?
   - Is there any jump in the argument where a sceptic could say "wait, how do you get from X to Y"?
   - Are confidence levels marked — what is confirmed vs. what is a working hypothesis?

   **Deferral risk check:**
   - Is there anything in the deck that gives the exec an easy reason to delay?
   - Vague next steps: "we'll follow up" → Fix: "Lorian will send the implementation plan by [date]"
   - Unanswered objections: if a major objection is not addressed in Safety, it will be raised and the meeting will lose momentum

9. **Deliver the stress-test verdict:**
   - Ready for delivery (with any final tweaks noted)
   - Needs rework (with specific slides and issues identified)

## Outputs

All outputs delivered in the conversation. No file saved unless requested.

Step 2 output: Slide skeleton (table with AVSPS role, headline, content type, narrative link, cut test)
Step 3 output: Content brief per slide (headline, bullets/visual, data reference, talking point)
Step 4 output: Stress-test results (checklist + verdict + specific items to fix)

## Guidelines

- The skeleton is not optional — building slides without a skeleton is the most common cause of decks that need to be rebuilt from scratch
- The Safety section is non-negotiable — if it is missing, add it before stress-testing
- The headline test: if someone read only the headlines, would they understand the argument? Apply this before finalising the skeleton
- Keep slides out of PowerPoint until the skeleton and content brief are approved — it is much faster to change a table than rebuild slides
- After delivering the skeleton, ask: "Read the headlines in order. Does this tell the story end-to-end without any content?"
- After the stress-test, flag: "The most common failure in the stress-test is a vague next step. An exec meeting that ends without a committed decision and a named owner has failed."
