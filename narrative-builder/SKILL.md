---
name: narrative-builder
description: >
  This skill should be used when the user wants to construct a full performance
  narrative from analysed metrics and cluster hypotheses — selecting and applying
  the right world-class framework to produce a narrative that gives an executive
  team a clear decision, not just a report. Takes cluster hypotheses, cross-domain
  connections, and strategic context — produces a structured narrative ready to
  feed into Recommendation Shaping and Exec Presentation Builder.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: performance-analysis
  step: "4"
---

# Narrative Builder

Construct the full performance narrative from cluster hypotheses — selecting and applying the right world-class framework to produce a narrative that drives a decision, not a debrief.

## The Standard

A performance narrative is ready when an executive who reads only the opening sentence knows:
1. What the most important business development is
2. What it means for value creation
3. What decision is being asked of them

If all three are not immediately clear, the narrative is not ready.

## Framework Selection

The skill selects the framework that best fits the situation. Lorian approves the choice before the narrative is built.

| Framework | Best for | Structure |
|-----------|---------|-----------|
| **Pyramid Principle (Minto)** | Complex multi-metric situations where the conclusion is clear but the evidence is layered | Answer → Key lines of argument → Supporting evidence |
| **SCQA (McKinsey)** | Situations with a clear tension or inflection point that needs to be surfaced | Situation → Complication → Question → Answer |
| **Narrative Arc** | Situations where the business story has a clear before/after structure | Current state → Tension → Turning point → Resolution → Call to action |
| **Decision-Maker's Frame** | High-stakes presentations where the exec needs to be moved from scepticism to action | What they believe now → What they need to believe → Evidence that bridges the gap → The ask |
| **Inverted Pyramid** | Time-pressured exec environments — lead with the most important thing | Most critical insight → Supporting insights → Background evidence |

The skill explains why the chosen framework was selected so Lorian builds the underlying skill, not just the output.

## Workflow

1. **Gather inputs** — Collect from the user:
   - Cluster hypotheses from Step 3 (all of them — including contradictions)
   - Cross-domain connections identified during analysis
   - Forward-looking signals (what happens if trends continue)
   - Strategic context: what is the business trying to achieve? What are the PE sponsor's priorities?
   - Confidence levels for each hypothesis (from the Performance Analyst skill)
   - Audience for the narrative (manager review vs. exec team vs. PE sponsor)

2. **Select the framework** — Based on the inputs, recommend a framework with a one-sentence rationale:
   - "I recommend SCQA because there is a clear complication (pipeline is below coverage target) in an otherwise stable situation, and the question (whether to treat this as a short-term timing issue or a structural sales effectiveness problem) frames the decision the exec team needs to make"
   - Confirm with the user before proceeding

3. **Identify the 1-3 most important insights** — Before writing the narrative, establish the hierarchy:
   - What is the single most important thing the data is showing?
   - What are the 2 supporting insights that strengthen or contextualise the lead?
   - What is left in the background (relevant but not central to the decision)?
   - This hierarchy determines the narrative structure — the most important insight drives the opening

4. **Map cross-domain implications** — Explicitly trace the dependency chain:
   - Example: Pipeline coverage at 2.1x (below 3x target) → Q4 ARR attainment at risk → cash flow impact in H1 next year → hiring plan may need to be delayed → product roadmap investment at risk
   - These chains are often where the most important value creation implications live
   - Every chain must end at a decision the exec team can make

5. **Identify the forward-looking signal** — The narrative must include what is about to happen:
   - If current trends continue for 2-3 periods, what does the business look like?
   - What is the earliest leading indicator that the trend is reversing (positive or negative)?
   - This is often the most valuable output: it converts historical reporting into a forward-looking signal

6. **Write the narrative** — Apply the selected framework. Rules:
   - Every paragraph serves the decision — cut anything that is interesting but not decision-driving
   - State confidence levels explicitly: "We are confident that X; we believe but have not yet confirmed that Y; we need SME input to determine Z"
   - Do not present hypotheses as conclusions — mark what is confirmed vs. what needs validation
   - The closing statement of the narrative must specify the decision the business needs to make

7. **Coherence test** — Before delivering, test:
   - Does the narrative hold together, or are there unresolved contradictions?
   - Does the opening sentence pass the 90-second test: would an exec know what they are being asked to decide?
   - Are the confidence levels marked clearly?
   - Is the forward-looking signal explicit?

8. **SME validation flags** — Mark which parts of the narrative:
   - Are confirmed by the data with high confidence (present as conclusions)
   - Are hypotheses that need SME validation (present as working hypotheses)
   - May be challenged by the SME (prepare for revision after Step 6)

## Outputs

Narrative delivered in the conversation. No file saved unless requested.

Each response includes:
- Framework selected with rationale
- Insight hierarchy (lead / supporting / background)
- Full narrative applying the framework
- Cross-domain dependency chain
- Forward-looking signal
- SME validation flags (what may change after Step 6)

## Guidelines

- The framework is a tool, not a cage — if the data doesn't fit cleanly, say so and explain the adaptation
- Never present a hypothesis as a conclusion — credibility is destroyed once in the exec room if an assumption turns out to be wrong
- The narrative must be revised after Step 6 (SME interview) — make it easy to update by clearly marking hypothesis vs. confirmed insight
- Shorter is always better: a 3-paragraph narrative that drives a decision is better than a 10-paragraph narrative that doesn't
- After delivering the narrative, ask: "Which parts of this are you least confident about? Let's flag those as explicit hypotheses before the SME interview"
- Proactively suggest: "Read the opening sentence aloud. If you wouldn't be comfortable saying those exact words to your CEO tomorrow, the narrative is not ready"
