---
name: formula-writer
description: >
  This skill should be used when the user wants to write an Excel formula, Power Query M code snippet,
  or DAX measure from a plain-English description. Takes a description of what needs to be calculated,
  where the data lives, and any conditions — and produces a complete, explained formula ready to use.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: model-build
  step: "6, 7"
---

# Formula Writer

Write Excel formulas, Power Query M code, and DAX measures from plain-English descriptions.

## Workflow

1. **Gather inputs** — Collect from the user:
   - What needs to be calculated (plain-English description)
   - Where the source data lives (sheet name, column name, table name, or Power Pivot table)
   - Whether the output should be a single value, a column, or a dynamic array
   - Any conditions or exceptions (e.g. "only for won deals", "exclude blanks", "last 12 months only")
   - Which tool to use: Excel formula, Power Query M code, or DAX measure (infer from context if obvious)

2. **Clarify if needed** — If the description is ambiguous or the data structure is unclear, ask one clarifying question before writing. Do not write a formula based on assumptions that might be wrong.

3. **Write the formula** — Produce the complete formula, M code, or DAX measure. Follow these rules:
   - Excel: prefer dynamic array functions (FILTER, XLOOKUP, UNIQUE, SEQUENCE) over legacy approaches; use structured table references where possible; use LET for complex multi-step calculations; always wrap in IFERROR or IFNA where errors are likely
   - Power Query M: write clean, readable M code with comments; handle type mismatches and null values explicitly; use parameters for file paths and variable inputs
   - DAX: use CALCULATE with explicit filter context; comment on filter context implications; note whether it should be a measure or calculated column

4. **Explain the formula** — Provide a line-by-line breakdown of what each part does, written so Lorian can understand and maintain it.

5. **Flag edge cases** — List 2-3 situations where the formula might break or produce unexpected results, and how to handle them.

6. **Offer alternatives** — If there is a meaningfully different approach (e.g. dynamic array vs. helper column), briefly describe the trade-off and recommend which to use.

7. **Performance note** — If the formula is likely to slow down the workbook (volatile functions like INDIRECT, OFFSET, NOW; very large ranges; complex array calculations), flag it and suggest a more efficient alternative.

## Outputs

Formula output is delivered in the conversation — no file saved.

Each response includes:
- The complete formula/code in a code block, ready to copy
- Line-by-line explanation
- Edge cases and how to handle them
- Alternative approach (if relevant)
- Performance note (if relevant)

## Guidelines

- Never guess at column names or data structure — ask if unsure
- Always prefer the most modern, maintainable approach over legacy formulas
- Write formulas Lorian can understand, not just formulas that work
- If the calculation is complex, suggest breaking it into named intermediate steps using LET (Excel) or step-by-step M code stages
- After delivering the formula, ask: "Does this give you what you need, or would you like me to adjust anything?"
- Proactively suggest if the same calculation would be better handled in Power Pivot (DAX) vs. Excel, or vice versa
