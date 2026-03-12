---
name: model-architecture-designer
description: >
  This skill should be used when the user wants to design the architecture of an Excel financial model
  before building it. Takes a business question, KPI list, and data structure — produces a full model
  blueprint including worksheet map, input/output structure, scenario logic, and navigation design.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: model-build
  step: "5"
---

# Model Architecture Designer

Design the full blueprint for an Excel financial model before a single cell is built.

## Workflow

1. **Gather inputs** — Collect from the user:
   - The business question the model answers
   - The confirmed KPI list (from kpi-recommender or Lorian's own list)
   - How the data arrives (Power Query output structure, or manual input)
   - Whether scenarios/assumptions switching is needed (how many scenarios)
   - Who will use the model (Lorian only, or shared with colleagues/execs)
   - Whether visuals stay in Excel or move to Power BI

2. **Propose worksheet structure** — Design the worksheet map. Standard structure for a SaaS financial model:

   | Sheet | Purpose | Colour code |
   |-------|---------|-------------|
   | README | Navigation guide, version log, contact | Grey |
   | Raw Data | Power Query output — never edited manually | Blue |
   | Inputs | All assumption cells, scenario selectors, parameters | Yellow |
   | Calculations | All formula-driven calculations — no hardcoded values | White |
   | Outputs | Summary outputs referenced from Calculations | Green |
   | Visuals | Charts and dashboard | White |
   | Checks | Reconciliation checks and validation flags | Orange |

   Adapt this structure to the specific model — add, remove, or rename sheets based on the business question and KPI list.

3. **Design the Inputs sheet** — Specify:
   - Which assumptions live here (growth rates, conversion rates, benchmarks, targets)
   - Scenario switching design: if >1 scenario, use CHOOSE function with a single selector cell
   - Dropdown list design for scenario selector
   - Clear separation between input cells (yellow fill) and calculated cells (white/grey)
   - Time period selector (if the model covers multiple periods)

4. **Design the Calculations sheet** — Specify:
   - Column structure (time periods across columns, metrics down rows — or reverse if more logical)
   - Where helper columns are needed (e.g. conditional flags for above/below benchmark)
   - Which calculations reference Inputs vs. Raw Data
   - Where Power Pivot (DAX) is more appropriate than Excel formulas

5. **Design navigation** — Specify:
   - README sheet with hyperlinks to each section
   - Named ranges for key cells
   - Tab colour coding convention
   - Freeze panes recommendations
   - Any user guidance to embed directly in the model (input instructions, notes)

6. **Flag critical decisions** — Identify the 3-5 architecture decisions that will be expensive to change later:
   - e.g. "If you put calculations in the same sheet as raw data, you'll struggle to update Power Query without breaking formulas"
   - e.g. "If you don't separate inputs from calculations now, scenario switching becomes very difficult later"

7. **Confirm the blueprint** — Present the full blueprint and ask: "Does this structure make sense for what you need to build? Any changes before we start?"

## Outputs

### `outputs/model-blueprint-[model-name].md` — Model Architecture Blueprint

Saved when the user confirms the design. Contains:
- Worksheet map (table with sheet name, purpose, colour code)
- Inputs sheet design
- Calculations structure
- Navigation design
- Helper column plan
- Critical architecture decisions and rationale
- Build sequence recommendation (which sheet to build first)

## Guidelines

- Never start designing the architecture until the KPI list is confirmed — architecture must serve the KPIs
- Always include a Checks sheet — models without reconciliation checks cannot be trusted
- Always include a README sheet for models that will be shared
- Flag immediately if the user wants to skip input/calculation separation — explain why this is a mistake
- After delivering the blueprint, recommend: "Build the Inputs sheet first, then Raw Data connections, then Calculations — this way every formula has something to reference from day one"
- Proactively surface: "Here is the decision that will cost you the most time to fix if you get it wrong at this stage..."
