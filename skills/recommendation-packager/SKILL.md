---
name: recommendation-packager
description: >
  This skill should be used when the user wants to frame their selected recommendation
  to minimise the exec's perceived cost of acting, build an objection map with response
  language and concession strategy, and assemble the complete recommendation package
  ready to feed into Exec Presentation Builder. Takes the evaluated options and
  recommendation selection — produces a framed recommendation statement, objection
  map, and full assembled package.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: recommendation-shaping
  step: "5, 6, 7"
---

# Recommendation Packager

> **v1 — Baseline.** This skill will be upgraded when the Executive Buy-in Presentation System course PDF arrives (29 March 2026). Framing techniques, buy-in frameworks, and objection response language will be significantly enhanced.

Frame the selected recommendation to minimise the exec's perceived cost of acting; build a complete objection map with response language; assemble the full recommendation package for WF4.

## The Standard

A recommendation is ready when an executive reads it and feels:
1. This is designed to help me succeed, not to expose someone or prove a point
2. I know exactly what I am being asked to decide
3. The cost of acting is lower than the cost of not acting

If the exec feels judged, cornered, or unclear about the ask, the recommendation is not ready.

## Workflow

1. **Gather inputs** — Collect from the user:
   - The selected option and rationale
   - The tension from Step 4: where is the political cost, and how has it been addressed?
   - Exec team profiles: communication style, incentives, what makes each person say yes
   - The explicit ask: what specifically is the exec being asked to decide or do in this meeting?

2. **Frame the recommendation** — The framing must achieve three things simultaneously:
   - Make the ask clear and specific
   - Connect to a value creation objective the exec already believes in
   - Make the exec feel supported, not evaluated

   **The recommendation structure:**
   > "In order to [value creation objective], I recommend [specific action] because [rationale from the data]. The decision I'm asking for is [explicit ask]."

   **Framing principles:**
   - Lead with the value creation objective, not the problem: "In order to protect ARR attainment" not "because pipeline is underperforming"
   - The recommendation is the data's conclusion, not Lorian's opinion: "The data points toward [X]" not "I think we should do [X]"
   - The exec is being offered an opportunity, not presented with a problem to solve: frame what success looks like, not just what failure looks like
   - Sensitive implications must be reframed: if the recommendation implies underperformance in someone's team, find language that positions the recommendation as supporting that person's success
     - Instead of: "The sales team's conversion rate has dropped and needs to be fixed"
     - Use: "To give the sales team the best chance of closing the Q4 pipeline, they need [specific support]"

3. **Make the ask explicit** — The single most common failure in executive recommendations is an implicit ask. The exec receives the analysis and recommendation but is not told what they are being asked to do in this meeting.

   The explicit ask answers: "What decision, commitment, or action do I need from you before we leave this room?"

   **Explicit ask formats:**
   - "I'm asking for your approval to [specific action] before [date]"
   - "I need you to align [name] on [specific point] before [date]"
   - "I'm asking for [resource/budget/headcount commitment] to begin [specific action]"
   - "I need this group to agree on [specific decision] today so that [team] can begin [specific action] this week"

   If there is no explicit ask, there is no recommendation — only a presentation.

4. **Quantify the upside and the cost of inaction** — Restate both in exec-relevant terms:
   - Upside: "If we act on this by [date], the probability of hitting ARR target increases from [X]% to [Y]%"
   - Cost of inaction: "If we continue on current trajectory, the Q4 shortfall is estimated at £[X]m — and the impact on the exit multiple is [Y]"
   - Connect to what the PE sponsor is watching: "This directly affects the metric Meridian will use to evaluate management team execution at the next board meeting"

5. **Build the objection map** — For each of the 3-5 most likely objections:

   **Objection classification:**
   | Type | Description | Response strategy |
   |------|-------------|-------------------|
   | **Analytical** | "The data doesn't support that conclusion" | Acknowledge, then show the evidence chain; invite them to identify which specific assumption they disagree with |
   | **Political** | "That would create problems with [colleague]" | Acknowledge the relationship concern; reframe the recommendation as supporting that colleague; offer to include them in the solution design |
   | **Resource** | "We don't have the budget/people for this" | Acknowledge the constraint; show the cost of not acting; propose a phased approach that fits within constraints |
   | **Timing** | "Now isn't the right time" | Acknowledge the timing concern; name the cost of delay specifically; identify the latest acceptable decision point |
   | **Credibility** | "How confident are you in this analysis?" | Acknowledge uncertainty honestly; show what you are confident in vs. what is a working hypothesis; the SME validation gives this credibility |

   **For each anticipated objection:**
   - State the objection in the exec's likely words
   - Classify it (analytical / political / resource / timing / credibility)
   - Write the response: acknowledge → hold the recommendation → redirect to value creation
   - Note who in the room is most likely to raise this objection
   - Identify the "hold the line" language — the sentence that holds the recommendation under pressure without being adversarial

6. **Design the concession strategy** — Every strong recommendation needs one prepared concession that can be offered without compromising the core:
   - The concession gives the exec a face-saving path to yes ("we can start smaller and scale if the first phase shows results")
   - The concession does not dilute the underlying recommendation — it adjusts scope, timing, or phasing, not the core direction
   - The concession is offered, not surrendered — it signals flexibility without weakness: "I'm open to a phased approach if that makes the decision easier — the important thing is that we begin"
   - Never offer the concession unprompted — hold it in reserve for when genuine resistance requires a bridge

7. **Assemble the recommendation package** — Compile all elements into a coherent document that flows from insight to decision:

   **Package structure:**
   1. Decision frame (one sentence — from Step 1)
   2. Value creation anchor and success metrics (from Step 2)
   3. Options evaluated (3 options with evaluation summary — from Steps 3-4)
   4. Recommended option with rationale (from Step 5)
   5. Explicit ask (from Step 5)
   6. Cost of inaction (restated)
   7. Objection map with responses (from Step 6)
   8. Concession in reserve (from Step 6)

   **Coherence check before delivering:**
   - Does the package flow: insight → decision → options → recommendation → ask?
   - If the exec read only the decision frame, the recommendation, and the ask — would they know exactly what they are being asked to decide and why it matters?
   - Is every element present? (A missing ask means the package is incomplete)

## Outputs

All elements delivered in the conversation. No file saved unless requested.

Each response includes:
- Framed recommendation statement (formatted)
- Explicit ask (formatted)
- Cost of inaction restatement
- Objection map (3-5 objections with response language)
- Concession strategy
- Full recommendation package (assembled and coherence-checked)

## Guidelines

- The recommendation belongs to the data, not to Lorian — every framing choice reinforces this
- Sensitive implications require reframing, not softening — the insight stays intact, the language changes
- The explicit ask is not optional — if it is missing, go back and add it before the package is considered complete
- Consult Agent 11 (Influence) for political framing and pre-meeting coalition; Agent 09 (Communication) for recommendation language; Agent 10 (EQ) to identify which objections trigger reactive defaults; Agent 12 (Conversational Intelligence) for objection response language
- After delivering the package, ask: "Is there anyone in that room whose objection you don't feel prepared for? Let's role-play it now."
- Proactively flag: "The concession is a negotiating tool — it is most powerful when held in reserve. Don't offer it in the opening presentation."
