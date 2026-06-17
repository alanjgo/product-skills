---
name: weekly-update
description: Prepare concise weekly updates for squad projects from Linear, Granola, and Notion context. Use when the user wants a Friday summary of what happened this week and what is planned next week for projects.
license: MIT
---

# Weekly Project Update

Summarize active projects into a short weekly update focused on progress, decisions, and next steps.

## Workflow

1. Identify relevant projects inside the squad.
2. Prioritize projects in `Co-conception`, `Framing`, or `Discovery` style phases, based on the available Linear status labels.
3. Gather recent project information from:
   - Linear updates
   - Granola notes
   - Notion pages
4. Write a short block for each project.

## Output

```md
## [Nom du projet]

### This week
- Maximum 3 bullets
- Maximum about 30 words per bullet

### Next week
- Maximum 3 bullets
- Maximum about 30 words per bullet
```

## Style

- Be very synthetic.
- Highlight decisions, concrete progress, and key next steps.
- If tools are incomplete, work from the user-provided context without blocking.
