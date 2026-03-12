---
name: sme-interview-designer
description: >
  This skill should be used when the user wants to design a structured interview
  with a business stakeholder (e.g. Head of Sales, CTO, CS leader) to extract
  genuine intelligence and context behind financial model data — without triggering
  defensiveness or getting a managed narrative. Takes the hypotheses to validate,
  the SME profile, and the meeting context — produces a complete interview guide
  with questions, sequencing, framing, and deflection probes.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: performance-analysis
  step: "5"
---

# SME Interview Designer

Design structured, unbiased intelligence-gathering interviews with business stakeholders — extracting genuine context behind the numbers without triggering defensiveness.

## The Core Challenge

A finance professional asking a functional leader about their own performance data creates a structural threat response. The SME knows what the numbers show. They have prepared their narrative. The default interview produces the managed version — not the intelligence. This skill is designed to defeat that dynamic.

## Workflow

1. **Gather inputs** — Collect from the user:
   - The hypotheses that need validation (from the full narrative, Step 4)
   - The SME's domain, role, and level of seniority
   - The SME's likely incentives (what do they want the data to show?)
   - The SME's likely defensive triggers (what topics will make them guard information?)
   - Sensitivity level: are the hypotheses confirming concerns the SME already feels bad about, or raising new issues?
   - Meeting format: time available, formal or informal, 1:1 or with others present

2. **Design the opening frame** — The first 60 seconds determines whether the SME gives genuine intelligence or a PR performance. The frame must:
   - Position the meeting as learning, not evaluation: "I want to understand what's really driving these numbers — your perspective is something the model can't give me"
   - Signal curiosity, not suspicion: "I have some hypotheses I'd like to test with you — please push back where I'm wrong"
   - Remove the audit dynamic: avoid anything that positions Lorian as assessing the SME's performance
   - Set a collaborative tone: "I'm trying to build a picture that helps the business make better decisions — you know this domain better than the data does"

3. **Sequence the questions** — Always move from safe to sensitive:

   | Phase | Question type | Purpose |
   |-------|--------------|---------|
   | **Rapport** | Open, positive, their domain | Establish safety; let them speak without judgment |
   | **Landscape** | Open exploration of the domain | Understand their mental model before testing your hypotheses |
   | **Hypothesis testing** | Neutral, not leading | Test specific hypotheses without revealing the conclusion |
   | **Sensitive probing** | Careful, curiosity-led | Explore the areas most likely to trigger defensiveness |
   | **Forward-looking** | Future-focused | Reduce threat; most people are more comfortable about what they're going to do than what they've done |
   | **Closing** | Reflective | "If you could change one thing about how this is being tracked/managed, what would it be?" |

4. **Design the questions** — For each hypothesis, produce 1-2 questions that:
   - Are open-ended (how, what, tell me about) — never yes/no
   - Do not contain the conclusion (never ask "why is pipeline coverage declining?"; ask "how would you describe the quality of the pipeline right now compared to 6 months ago?")
   - Invite the SME to be the expert (they are — treat them as one)
   - Can be answered in multiple ways — you want to see which direction they go

   **Question types to use:**
   - **Open landscape:** "Walk me through how [metric] has been tracking this quarter from your perspective"
   - **Hypothetical:** "If conversion rates were to fall further from here, what would you expect the main driver to be?"
   - **Reflective:** "What's the most surprising thing the data is showing you right now?"
   - **Devil's advocate:** "Someone looking at this data might conclude [X] — how would you respond to that?"
   - **Future-focused:** "What are you most focused on changing in the next 90 days?"

5. **Prepare deflection probes** — For each sensitive hypothesis, anticipate the managed response and prepare a follow-up:
   - **Managed response pattern:** Attribute to external factors, minimise, redirect to positives, promise future improvement without acknowledging current reality
   - **Probe approach:** Acknowledge their point, then re-enter from a different angle: "That makes sense — and within that context, how much of [X] do you feel is within the team's control to change?"
   - **Silence as a probe:** After a managed response, pause. Most people fill silence with more honest information.
   - **Specificity probe:** "Can you give me a specific example of that?" — vague answers collapse under specificity requests

6. **Produce the interview guide** — Deliver:
   - Opening frame (exact words to use)
   - Full question sequence with rationale for each
   - Follow-up probes for the 2-3 most sensitive areas
   - What a good answer looks like vs. a defensive non-answer (for each sensitive question)
   - What to listen for that the SME won't say directly (body language flags, topic avoidance, over-explanation)
   - Closing question

7. **Post-meeting debrief prompt** — Provide a structured debrief guide:
   - What did the SME confirm? What did they challenge?
   - Where did they volunteer information (high credibility signal)?
   - Where did they deflect or become vague (investigation flag)?
   - What key phrases did they use that contain strategic intelligence?
   - What new hypotheses emerged that weren't in the model?

## Outputs

Interview guide delivered in the conversation. No file saved unless requested.

Each response includes:
- Opening frame (exact wording)
- Full question sequence (8-12 questions) with rationale
- Deflection probes for sensitive areas
- Good answer vs. defensive non-answer guide
- Post-meeting debrief structure

## Guidelines

- Never write leading questions that contain the hypothesis — this collapses information quality immediately
- The SME is an expert in their domain; the interview works when they feel that is recognised
- Fewer questions with better follow-up probes beats a long list of questions with no depth
- The most valuable intelligence often comes after the interview is nominally over — prepare a casual closing moment
- Draw on Agents 10 (EQ), 11 (Influence), and 12 (Conversational Intelligence) before finalising the guide — each brings a dimension this skill alone cannot fully cover
- After delivering the guide, ask: "Would you like to do a practice run of the most sensitive question? Role-play helps more than reading."
- Proactively flag: "The question you most want to ask is usually the one that will trigger the most defensiveness — let's find a sideways route to the same intelligence"
