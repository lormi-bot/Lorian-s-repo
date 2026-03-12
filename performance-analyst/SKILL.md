---
name: performance-analyst
description: >
  This skill should be used when the user wants to analyse a financial metric or
  group of metrics from a model — moving from raw observation to value creation insight.
  Takes a metric description, domain context, and model data — produces a structured
  What/So What/Now What analysis using world-class analytical frameworks that go
  significantly beyond surface description.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: performance-analysis
  step: "2, 3"
---

# Performance Analyst

Apply world-class analytical frameworks to interpret financial metrics and metric clusters — moving from description to insight to value creation implication.

## Starting Mental Model

What/So What/Now What (WSN) is the starting framework — a valid structure for organising interpretation. It is not the ceiling. This skill applies WSN as the output format while drawing on significantly more sophisticated analytical frameworks to determine what goes inside each level.

## Workflow

1. **Gather inputs** — Collect from the user:
   - The metric or visual being analysed (what it shows, including the number and movement)
   - Domain context: pipeline, ARR, P&L, activation, retention, or other
   - Time context: which period, vs. prior period, vs. budget/target
   - Benchmark context: what does good look like for this metric in a PE-backed SaaS business?
   - Any known business context that might explain the movement

2. **Classify the signal** — Before interpreting, determine what type of movement this is:

   | Signal type | Description | Analytical approach |
   |-------------|-------------|---------------------|
   | **Trend continuation** | Movement in the same direction as prior periods | Extrapolate; flag if rate of change is accelerating or decelerating |
   | **Inflection point** | Direction change — a metric that was improving is now worsening (or vice versa) | Treat as high-priority; identify the likely inflection driver |
   | **Outlier** | Single-period spike or drop inconsistent with trend | Investigate cause before drawing conclusions; may be noise |
   | **Structural shift** | Sustained change in level or slope that represents a new normal | Most important signal type; hardest to detect early |
   | **Noise** | Movement within normal variation — no actionable signal | Do not over-interpret; flag as noise and move on |

3. **Apply the analytical frameworks** — For each metric, apply the relevant frameworks:

   **Signal vs. noise:**
   - Is the magnitude of movement meaningful relative to the baseline? (A 5% move on a volatile metric is different from a 5% move on a stable one)
   - Is this confirmed by multiple metrics, or is it a single data point?
   - Is there a plausible business explanation for the movement, or does it appear random?

   **PE lens — what a sponsor would ask:**
   - Does this metric confirm or threaten the value creation plan?
   - Is this movement within the range that was modelled at acquisition?
   - What does this imply for the exit multiple if the trend continues?
   - What action does this demand from the management team?

   **Forward-looking signal:**
   - If this trend continues for 2-3 periods, what does the business look like?
   - Is this a leading indicator of something that will show up in a lagging metric later? (e.g. declining pipeline coverage → future ARR miss)
   - What is the earliest point at which management could intervene to change the trajectory?

   **Cross-domain impact:**
   - What does this metric imply for other parts of the business?
   - Map the dependency chain: sales performance → ARR → cash → hiring capacity → product investment
   - Flag which downstream metrics to watch as a result of this signal

4. **Produce the WSN output** — Structure the interpretation:

   - **What:** State the fact precisely — the metric, the movement, the magnitude, the context (vs. prior period, vs. target)
   - **So What:** State the business implication — why this matters, what it changes, what it threatens or confirms. Be specific. "Revenue is growing" is not a So What. "Pipeline coverage falling below 3x in Q3 threatens Q4 ARR attainment by approximately 15-20%" is.
   - **Now What:** State the value creation action — what decision or action does this signal point toward? Be specific. "Investigate further" is not a Now What. "Challenge the CSO on whether the pipeline quality issue is a targeting problem (wrong prospects) or a conversion problem (right prospects, wrong sales motion)" is.

5. **Confidence and flags** — Always state:
   - Confidence level: **High** (clear signal, multiple confirming data points) / **Medium** (plausible but requires SME validation) / **Low** (ambiguous — do not present as conclusion)
   - What would change this interpretation: which assumptions or context would flip the So What or Now What?
   - SME validation needed: yes/no — and what specifically to ask

6. **Cluster synthesis (Step 3)** — When called for a cluster of related metrics:
   - Do the metrics in this cluster tell a coherent story, or do they contradict each other?
   - Reinforcing pattern: multiple metrics pointing in the same direction → higher confidence
   - Contradicting pattern: metrics in the same domain telling different stories → a question to resolve, not a conclusion to draw
   - Identify the hypothesis the cluster most strongly supports
   - Flag which hypothesis would be most valuable to validate with the SME

## Outputs

Analysis delivered in the conversation. No file saved unless requested.

Each response includes:
- Signal classification (trend type)
- What / So What / Now What (structured)
- Confidence level with rationale
- Cross-domain implications
- SME validation flags

## Guidelines

- WSN is the output format, not the analytical ceiling — the frameworks above determine what goes inside each level
- Never stop at What — if the So What is not clear, say so and ask for more context before guessing
- Now What must be a genuine value creation action — not "monitor" or "investigate"
- PE lens is always active — every metric is implicitly being read by a sponsor asking "does this create or destroy value?"
- After delivering the analysis, ask: "Does this match your reading, or are there aspects of the business context I'm missing that would change the interpretation?"
- Proactively flag when a metric cluster is contradictory rather than forcing a clean narrative — contradictions are often the most interesting signal
- After Step 3 (cluster synthesis), recommend: "Before moving to the full narrative, flag which hypotheses most need SME validation — don't present hypotheses as conclusions in the exec room"
