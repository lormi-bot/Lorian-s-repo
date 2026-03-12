---
name: decision-framer
description: >
  This skill should be used when the user wants to translate validated performance
  insights into a clear decision frame and value creation anchor for an executive
  recommendation. Takes the key insights from Performance Analysis, the decision
  owner, and strategic context — produces a one-sentence decision frame, cost-of-
  inaction statement, value creation anchor, and evaluation criteria for comparing
  options.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: recommendation-shaping
  step: "1, 2"
---

# Decision Framer

Translate validated performance insights into a crisp decision frame and value creation anchor — establishing what specifically needs to be decided, by whom, and what is at stake if nothing changes.

## The Standard

A decision frame is ready when the decision owner reads it and immediately understands:
1. What they are being asked to decide
2. Why this decision matters for value creation
3. What happens if they do nothing

If any of these three are unclear, the frame is not ready.

## Workflow

1. **Gather inputs** — Collect from the user:
   - The 1-3 key insights from WF2 (Performance Analysis) — the validated narrative
   - Who the decision owner is (the exec with the power and accountability to act)
   - Business performance targets: ARR, NRR, Rule of 40, or other relevant metrics
   - PE sponsor priorities: what does Meridian Capital Partners care most about right now?
   - Strategic context: what is the business trying to achieve and by when?

2. **Construct the decision frame** — The frame must:
   - Name one decision (not a theme, not a general concern — one specific decision)
   - Format: "The decision is whether to [specific action] in order to [specific value creation outcome]"
   - Name the decision owner explicitly: "This decision sits with [role]"
   - State what changes if the decision is made — and what stays the same if it is not

   **Common framing errors to diagnose and fix:**
   - Too vague: "We need to improve pipeline" → Fix: "The decision is whether to restructure the enterprise BDR team to focus exclusively on ICP accounts, in order to improve pipeline quality and protect Q4 ARR attainment"
   - Lorian's problem: "I think we should invest in sales enablement" → Fix: "The decision is whether to invest £X in sales enablement in Q4 to reduce ramp time and recover the ARR productivity gap"
   - Multiple decisions bundled: "We need to fix pipeline, improve conversion, and reduce churn" → Fix: sequence these — which is the most urgent decision? Present one at a time.
   - Wrong decision owner: Ensure the person being asked to decide is the person with actual authority and accountability

3. **Build the cost-of-inaction statement** — The exec needs to feel the cost of not deciding:
   - State what the trend looks like if current conditions continue (use the forward-looking signal from WF2)
   - Quantify where possible: "If pipeline coverage remains below 3x for another quarter, Q4 ARR attainment falls to 75-80% of target — a £Xm shortfall"
   - Connect to PE sponsor: "This would put the business outside Meridian's growth target for the year"
   - Make it a business problem, not a personal criticism — "the business is at risk of" not "the sales team has failed to"

4. **Set the value creation anchor** — All options will be evaluated against this anchor. It must be:
   - Specific: "increase probability of ARR above £Xm budget" not "improve performance"
   - Connected to what the exec team already believes in — the anchor must not require the exec to accept a new objective before evaluating options
   - Quantified where possible: "options that increase ARR attainment probability above 80% within 90 days"
   - Connected to the exit multiple: "this directly supports Meridian's 3x revenue growth target and the planned exit in 24 months"

5. **Define the evaluation criteria** — Establish the lens for comparing options before options are generated. Standard criteria for PE-backed SaaS:
   - **Value creation impact:** How much does this move the key metric?
   - **Speed of impact:** How quickly does this produce results? (90 days / 6 months / 12+ months)
   - **Cost:** Financial cost and resource requirement
   - **Relationship risk:** What relationships are put at risk by this option?
   - **Reversibility:** If this turns out to be wrong, how easy is it to undo?
   - **Change capacity:** Does the organisation have the capacity to execute this right now?

   Weight the criteria: which matters most for this specific decision? State the weighting explicitly before options are generated.

## Outputs

Decision frame delivered in the conversation. No file saved unless requested.

Each response includes:
- One-sentence decision frame (formatted and tested)
- Decision owner identification with rationale
- Cost-of-inaction statement (quantified where possible)
- Value creation anchor statement
- Evaluation criteria with relative weighting

## Guidelines

- One decision at a time — if there are multiple decisions, sequence them by urgency and impact; present one frame at a time
- The frame must belong to the exec, not to Lorian — "the business must decide" not "I believe we should"
- The cost-of-inaction is not optional — without it, the exec has no urgency to act
- Challenge vague frames until they become specific enough that a single person can be held accountable
- After delivering the frame, ask: "Would the [decision owner role] read this and immediately understand what they are being asked to decide? Or could they read it and feel it's someone else's problem?"
- Before proceeding to options, confirm: "Are you confident this is the right decision to put in front of the exec team? Changing the frame at Step 5 is expensive."
- Consult Agent 08 (Decision-Making) to challenge the frame quality; Agent 06 (Leadership) to confirm this is a CFO-level framing, not an FBP-level framing
