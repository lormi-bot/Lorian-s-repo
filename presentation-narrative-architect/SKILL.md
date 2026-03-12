---
name: presentation-narrative-architect
description: >
  This skill should be used when the user wants to build the overarching value
  creation narrative for an executive presentation — selecting and applying the
  right world-class framework to create the story arc that the entire deck is
  built around. Takes the recommendation package from Workflow 3 and the audience
  profile — produces the narrative spine, opening sentence, and story arc structure
  ready to feed into slide design.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: exec-presentation-builder
  step: "1"
---

# Presentation Narrative Architect

Build the overarching value creation story arc for an executive presentation — the spine that every slide must serve.

## Distinction from Narrative Builder (WF2)

The WF2 Narrative Builder produces an analytical interpretation narrative: what happened, what it means, what the business must decide. This skill produces a presentation narrative: a structured argument designed to move a specific exec audience from their current belief state to a committed decision. Same frameworks, different purpose and audience orientation.

## The Standard

The presentation narrative is ready when:
1. It is argumentative, not descriptive — it drives a decision, not just informs
2. One coherent thread runs from opening to close — no competing stories
3. The opening sentence could stand alone as the reason to act
4. A non-finance exec could follow it and know what they are being asked to decide

## Framework Selection

| Framework | Best for | Structure |
|-----------|---------|-----------|
| **AVSPS** (Action → Value → Safety → Proof → Next Step) | Most exec decision meetings — leads with the ask, builds the case | Ask → Why it matters → Address fears → Evidence → What happens next |
| **Pyramid Principle (Minto)** | Audiences who want the conclusion first, then evidence | Answer → Key supporting arguments → Data |
| **SCQA (McKinsey)** | Situations with a clear complication that creates urgency | Situation (stable) → Complication (what changed) → Question (what do we do?) → Answer |
| **Narrative Arc** | Audiences who respond better to story than argument | Current state → Tension → Turning point → Resolution → Call to action |
| **Decision-Maker's Frame** | Sceptical audiences who need to be moved through a belief sequence | Current belief → Evidence that creates doubt → New belief → Call to action |

**AVSPS is the default for WF4** — it is the Executive Buy-in Presentation System structure and directly addresses the most common failure in finance presentations (burying the ask). Other frameworks supplement or replace AVSPS based on the specific audience and recommendation type.

## Workflow

1. **Gather inputs** — Collect from the user:
   - Recommendation package from WF3 (decision frame, recommendation, explicit ask, cost of inaction)
   - Validated insights from WF2 (the 1-3 most important insights that support the recommendation)
   - Audience profile: who is in the room, their current belief state, what they care about most, their relationship to the recommendation
   - PE sponsor context: does Meridian Capital's value creation thesis need to be explicitly invoked?
   - Stakes: is this a major strategic decision, a resource approval, or a course correction?

2. **Select the framework** — Recommend with explicit rationale:
   > "I recommend [framework] because [1-2 sentences on why this audience and recommendation type calls for this structure]. The alternative was [alternative] — I rejected it because [reason]."

   Confirm with Lorian before building the narrative.

3. **Anchor to the value creation goal** — The narrative starts with what the business is trying to achieve:
   - "Aria Software's goal is to hit £[X]m ARR by [date] and deliver [Y]x return for Meridian Capital Partners"
   - This is not context-setting — it is the frame against which everything else is evaluated
   - Every exec in the room should nod when they hear this

4. **Build the narrative structure** — Apply the selected framework to produce the five elements:

   **A — The opening (Action / Answer / Complication):**
   The first sentence must be the most important sentence in the presentation. It states what the exec is being asked to decide and why now.
   - AVSPS: "I'm here to ask for [specific decision] — here's why it is the most important thing this team can act on in Q4"
   - Pyramid: "The data points toward [recommendation] — I'll show you the evidence in a moment, but I want to be direct about the ask upfront"
   - SCQA: "We are on track for [X]. In Q3, [Y] changed. The question is what we do about it before Q4 closes."
   Avoid: opening with context, agenda slides, or "thanks for making the time."

   **B — The value (Why this matters):**
   Quantify what is at stake — what does acting look like vs. not acting?
   - "If we act on [recommendation] by [date], the probability of hitting ARR target increases from [X]% to [Y]%"
   - "If current trends continue, the Q4 shortfall is estimated at £[X]m — and this compounds into [Y] at exit"
   - Connect to Meridian Capital's value creation thesis where it strengthens urgency

   **C — The safety (Reduce the cost of acting):**
   Address the exec's fears before they raise them — this is what most finance presentations skip entirely.
   - "The main concern I anticipate is [X]. Here is how we have designed the recommendation to address that."
   - "This does not require [the thing they fear most] — it requires [what it actually requires]"
   - Reframe sensitive implications: position the recommendation as supporting people, not criticising them

   **D — The proof (Evidence):**
   The evidence that justifies the recommendation — after the ask, not before.
   - The 2-3 most compelling data points that clinch the argument
   - The SME validation: "the Head of Sales confirmed that [X]"
   - Not all the data — only the data that matters for the decision

   **E — The close (Next step):**
   The explicit ask, stated twice — once in the opening, once in the close.
   - "I'm asking this group to commit to [specific action] before we leave this room today"
   - Next steps are specific: owner, action, date
   - The meeting does not end without these being named

5. **Write the opening sentence** — Separately, draft 2-3 versions of the opening sentence and select the strongest:
   - Each version should communicate the recommendation and the ask in one sentence
   - Test: could someone hear only this sentence and know what the meeting is about?
   - The opening sentence is the most rehearsed sentence in the presentation

6. **Coherence check** — Before delivering:
   - Is there one thread from opening to close, or multiple competing stories?
   - Is every element argumentative, not descriptive?
   - Is the safety section present? (Most presentations are missing it)
   - Does the narrative work without the slides?

## Outputs

Narrative delivered in the conversation. No file saved unless requested.

Each response includes:
- Framework selected with rationale (and alternatives rejected)
- Written value creation narrative (5 elements: opening / value / safety / proof / close)
- Opening sentence (2-3 options, recommended choice)
- Coherence verdict

## Guidelines

- AVSPS is the default — override only when the audience or recommendation type specifically calls for a different structure
- The safety section is non-negotiable — skip it and the objections come in the room instead of being pre-empted
- Lead with the ask — this is the hardest habit change for finance professionals and the most impactful
- The narrative must work without slides — if the spoken narrative is weak, the slides won't save it
- After delivering, ask: "Say the opening sentence out loud. Does it feel natural, or does it feel like you're presenting rather than talking?"
- Proactively flag: "The most common mistake at Step 1 is writing a narrative that describes rather than argues. Every sentence should advance the decision — if a sentence doesn't do that, cut it."
