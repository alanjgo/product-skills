---
name: data
description: Draft readable PostgreSQL queries for Staycation business questions. Use when the user asks for SQL, analysis logic, or data exploration on Staycation marketplace data, especially users, hotels, packages, inventory, publishing state, or booking performance.
license: MIT
---

# Staycation SQL

Write simple, readable PostgreSQL queries and ground them in the available schema files before making assumptions.

## Schema source

Read [references/schema-sources.md](references/schema-sources.md) before writing non-trivial queries.

Use this priority order:

1. `data/db_schema_snowflake.json`
2. `data/db_schema.json`

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

1. `Rappel de la question`
2. `Hypothèses` when needed
3. `Requête SQL`
4. `Notes / validations éventuelles`

## Business context

- Staycation is a marketplace for hotel experiences and packages.
- Users buy packages.
- Hotels manage opening inventory.
- Packages often need to be published to be visible.
