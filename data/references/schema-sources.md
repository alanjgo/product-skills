# Schema Sources

Use these local files as the source of truth for Staycation SQL requests.

## Priority order

1. `/Users/alanjego/Desktop/y/data/db_schema_snowflake.json`
2. `/Users/alanjego/Desktop/y/data/db_schema.json`

## Guidance

- Prefer the Snowflake schema file first.
- Fall back to the generic schema file only when the needed information is absent.
- State assumptions explicitly when neither file confirms a table, field, or relationship.
- Keep queries in PostgreSQL syntax unless the user explicitly asks for another dialect.
