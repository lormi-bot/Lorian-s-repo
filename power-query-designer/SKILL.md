---
name: power-query-designer
description: >
  This skill should be used when the user wants to design a Power Query data pipeline,
  write M code transformations, or set up an automated data ingestion architecture.
  Takes a description of the data source and transformation needed — produces M code,
  folder architecture recommendations, and documentation.
user_invocable: true
metadata:
  version: "1.0.0"
  workflow: model-build
  step: "3, 7"
---

# Power Query Designer

Design Power Query pipelines and write M code from plain-English descriptions.

## Workflow

1. **Gather inputs** — Collect from the user:
   - Description of the data source (file type: CSV/Excel/SharePoint/web, structure, key column names)
   - Whether this is a one-off load or a recurring pipeline (e.g. monthly snapshot refresh)
   - What the data needs to look like after transformation (target structure)
   - Any known data quality issues (inconsistent formats, nulls, duplicate rows, changing column names)
   - Whether multiple files need to be combined (folder-based ingestion)

2. **Design the architecture** — Before writing M code, propose the pipeline architecture:
   - For recurring snapshots: folder-based approach with date-stamped files, parameter query for folder path
   - For one-off loads: direct file connection
   - For multiple sources: staged queries (source → clean → combine → output)
   - Identify where each transformation stage should sit in the query chain

3. **Write the M code** — Produce complete, working M code for each query in the pipeline:
   - Include comments explaining each transformation step
   - Handle null values and type mismatches explicitly
   - Use Table.TransformColumnTypes to lock data types
   - Include error handling for missing columns (try/otherwise patterns)
   - Use parameters for file paths, folder locations, and date ranges that will change

4. **Document the pipeline** — Provide:
   - Folder structure recommendation with naming convention
   - Step-by-step instructions for adding a new monthly snapshot
   - What to do when the pipeline breaks (common failure modes and fixes)

5. **Flag risks** — Identify the 2-3 most likely ways this pipeline will break in future:
   - Column name changes in source files
   - New file formats or delimiters
   - Data type changes
   - Suggest defensive patterns for each

## Outputs

### `outputs/power-query-[model-name]-pipeline.md` — Pipeline Documentation

Saved when the user confirms the design. Contains:
- Pipeline architecture diagram (text-based)
- M code for each query in code blocks
- Folder structure and naming convention
- Monthly update instructions
- Failure mode guide

If the user does not want a file saved, deliver in the conversation only.

## Guidelines

- Always design architecture before writing code — a wrong architecture is expensive to fix
- Prefer parameter queries over hardcoded file paths — makes the pipeline portable
- For recurring pipelines, always include instructions for the monthly update process
- Flag when a transformation is complex enough to warrant splitting into separate queries for maintainability
- After delivering M code, ask: "Would you like me to walk through how to paste this into Power Query?"
- Proactively suggest: if the transformation is complex enough to warrant Power Pivot (DAX) instead, say so
