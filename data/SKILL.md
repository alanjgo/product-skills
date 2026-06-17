---
name: data
description: Draft readable PostgreSQL queries for business questions. Use when the user asks for SQL, analysis logic, or data exploration.
license: MIT
---

# SQL

Write simple, readable PostgreSQL queries and ground them in the available schema files before making assumptions.

## Schema source

[if empty, ask user to add their database schema as a json file and send instricutions to get database schema]. 

## Workflow

1. Restate the question briefly.
2. Identify the likely tables, joins, filters, grain, and output shape from the schema sources.
3. List any assumptions above the query if the schema or business rule is uncertain.
4. Write PostgreSQL that is easy to read:
   - clear aliases
   - consistent indentation
   - limited nesting when possible
5. Add short comments only for non-obvious logic.
6. If useful, suggest a validation check or an alternative version.

## Output

1. `Hypotheses` when needed
2. `SQL request`
3. `Additional notes or validations required`

## Business context

if empty, ask user to add company context, or specifities.
