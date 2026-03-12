---
name: option-generator
description: >
  This skill should be used when the user wants to generate a genuine range of
  distinct options for an executive decision and evaluate each honestly — including
  political cost — to identify where the analytically best option and the
  politically easiest option diverge. Takes the decision frame, value creation
  anchor, and evaluation criteria — produces 3 distinct options with evaluation
  matrix and political cost assessment.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: recommendation-shaping
  step: "3, 4"
---

# Option Generator

> **v1 — Baseline.** This skill will be upgraded when the Executive Buy-in Presentation System course PDF arrives (29 March 2026). Option generation and evaluation frameworks will be enhanced with course methodology.

Generate a genuine range of distinct options for an executive decision and evaluate each honestly — including the political cost that determines whether the right option will actually be taken.

## The Standard

Options are ready when:
1. They are genuinely distinct — not variations of the same approach at different intensities
2. One of them is the "do nothing" or "status quo" option — making the cost of inaction explicit
3. The evaluation is honest — including where the best option is also the hardest one politically

## Workflow

1. **Gather inputs** — Collect from the user:
   - Decision frame from Step 1 (what is being decided)
   - Value creation anchor and evaluation criteria from Step 2
   - Validated insights from WF2 (what the data shows)
   - Exec team context: risk appetite, change capacity, known political dynamics
   - Known constraints: time horizon, budget, relationships under pressure

2. **Generate the option range** — Apply the range test to ensure genuine distinctiveness:

   | Option archetype | Description | When to use |
   |-----------------|-------------|-------------|
   | **Do nothing / status quo** | Current trajectory continues — used to make cost of inaction tangible | Always include unless a decision has already been forced |
   | **Targeted fix** | A specific, bounded intervention in the area showing the problem | When the problem is localised and the root cause is clear |
   | **Structural change** | A change to how the organisation operates — processes, accountabilities, or team design | When the problem is systemic rather than isolated |
   | **Invest and accelerate** | Increase resources (people, budget, tools) to address the gap more aggressively | When the problem is primarily a capacity/speed issue |
   | **Deprioritise and refocus** | Stop doing something in order to do something else better | When the problem is resource allocation rather than absolute capacity |
   | **Strategic pivot** | A change to the business model, market focus, or strategic direction | When the problem reflects a structural market or positioning issue |
   | **Wait and watch** | Delay the decision to gather more information — only valid with an explicit review trigger | When the signal is genuinely ambiguous and the cost of a wrong decision is high |

   **Rules for option generation:**
   - No fewer than 3 options (excluding do-nothing if used)
   - No more than 4 options — beyond 4, execs don't choose, they defer
   - Options must be genuinely distinct: if options A and B would both require the same executive decision and the same owner, they are not distinct enough
   - Name each option concisely: the name should communicate the approach in 3-5 words

3. **Test option distinctiveness** — Before proceeding to evaluation, apply:
   - Could two people in the exec team simultaneously advocate for different options without contradicting each other? → If yes, the options are distinct
   - Does each option produce a meaningfully different business outcome at 12 months? → If not, merge them
   - Is there an option that a board member would consider too conservative, and one they would consider too bold? → The range is correct

4. **Evaluate options against criteria** — Build the evaluation matrix using the criteria from Step 2:

   For each option × each criterion:
   - Score: High / Medium / Low (or quantify where possible)
   - Note the key uncertainty: what would need to be true for this score to be wrong?

   Typical evaluation dimensions:
   - Value creation impact: what does this move the key metric by?
   - Speed to impact: 0-3 months / 3-6 months / 6-12 months / 12+ months
   - Financial cost: investment required
   - Organisational cost: change management burden, distraction from BAU
   - Relationship risk: which relationships does this put at risk?
   - Reversibility: if wrong, how hard to undo?

5. **Conduct the political cost assessment** — This is the step most finance professionals skip, and it is why recommendations fail. For each option:

   **Map the political cost:**
   - Who has to take action or change behaviour for this option to succeed?
   - Who loses something (power, budget, headcount, autonomy) if this option is chosen?
   - Who in the exec team feels implicitly criticised by this option?
   - What is the decision owner's perceived cost of proposing this to their peers?

   **Classify the cost:**
   - **Low:** The option requires no one to lose face, admit failure, or put themselves at risk
   - **Medium:** The option requires someone to change approach or allocate new resources, but doesn't threaten anyone's position
   - **High:** The option requires someone to be held accountable for underperformance, or requires the CEO/board to override a colleague's preference

   **The central tension:** Flag where the analytically best option has the highest political cost. This is the core tension of WF3 and must be made explicit before framing the recommendation. Options:
   - Find a way to reduce the political cost without diluting the analytical value (preferred)
   - Accept the political cost and prepare the exec for it
   - Choose a lower-cost option with a commitment to escalate if it doesn't work

6. **Present the evaluation** — Structure:
   - Options table: name, description, owner, evaluation scores
   - Political cost summary for each option
   - The tension statement: "Option 2 is the analytically strongest but carries the highest political cost because [X]. Options for managing this: [A], [B], [C]"
   - Recommendation signal: which option does the evaluation most strongly support? (This is an input to Step 5, not the recommendation itself)

## Outputs

Options and evaluation delivered in the conversation. No file saved unless requested.

Each response includes:
- 3-4 distinct options (including do-nothing where appropriate)
- Evaluation matrix with scores per criterion
- Political cost assessment for each option
- The tension statement (where best option ≠ easiest option)
- Recommendation signal (input to Step 5)

## Guidelines

- The do-nothing option is not pessimism — it is the clearest way to make the cost of inaction tangible
- Never generate options that are designed to make one option look obviously right — this destroys credibility when the exec realises what happened
- The political cost assessment is not optional — it is the primary reason recommendations fail in the exec room
- Consult Agent 07 (Change Management) to assess whether the organisation has the change capacity for each option; Agent 28 (Corporate Transformation) for structural options; Agent 11 (Influence) for political cost mapping
- After delivering the evaluation, ask: "Are you comfortable bringing the analytically strongest option even if it has a high political cost? Or do we need to work on reducing that cost before Step 5?"
- Flag: "If you are leaning toward a lower-cost option primarily because of political risk, name that explicitly — a consciously political choice is more defensible than an accidentally weak recommendation"
