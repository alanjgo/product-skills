# Skills for Product Managers

Open-source agent skills for product decision work:

- `ab-test`: analyze A/B test results as a senior product manager and turn experiment metrics into a rollout, rollback, or retest decision.
- `business-opportunity`: size and assess Staycation business opportunities through GMV levers.
- `data`: draft readable PostgreSQL queries for Staycation marketplace data questions.
- `documentation`: write concise product documentation for mixed product, business, marketing, and tech audiences.
- `point-etape`: turn rough meeting notes into a decision-ready French checkpoint update.
- `prd`: draft or improve concise, outcome-driven PRDs.
- `stress-test`: pressure-test a product concept, spec, launch plan, roadmap proposal, or recommendation through a Staycation CEO/CPO lens.
- `weekly-update`: prepare concise weekly French updates for PELU projects.

Each skill is a self-contained folder with:

- `SKILL.md`: the agent instructions and trigger metadata.

The repository follows the [Agent Skills specification](https://agentskills.io/specification): each skill directory contains a `SKILL.md` file with YAML frontmatter and Markdown instructions. No runtime-specific configuration is required.

## Installation

Clone the repository:

```bash
git clone https://github.com/alanjgo/product-skills.git
```

Then install each skill according to your agent runtime's convention. The portable source of truth is each `SKILL.md` file:

- `product-skills/ab-test/SKILL.md`
- `product-skills/business-opportunity/SKILL.md`
- `product-skills/data/SKILL.md`
- `product-skills/documentation/SKILL.md`
- `product-skills/point-etape/SKILL.md`
- `product-skills/prd/SKILL.md`
- `product-skills/stress-test/SKILL.md`
- `product-skills/weekly-update/SKILL.md`

For agents that support local skill folders, copy or symlink the skill folders into that agent's skills directory:

```bash
mkdir -p ~/.agent/skills
cp -R product-skills/ab-test ~/.agent/skills/
cp -R product-skills/business-opportunity ~/.agent/skills/
cp -R product-skills/data ~/.agent/skills/
cp -R product-skills/documentation ~/.agent/skills/
cp -R product-skills/point-etape ~/.agent/skills/
cp -R product-skills/prd ~/.agent/skills/
cp -R product-skills/stress-test ~/.agent/skills/
cp -R product-skills/weekly-update ~/.agent/skills/
```

If your agent does not have a skill-folder system, paste or reference the relevant `SKILL.md` content in the agent's system instructions, project instructions, or custom prompt library.

### Install with `npx skills`

You can also install directly from this public GitHub repository with the `skills` CLI. Publishing to `skills.sh` is not required.

List the skills available in the repository:

```bash
npx skills add alanjgo/product-skills --list
```

Install both skills:

```bash
npx skills add alanjgo/product-skills --skill '*' --yes
```

Install only one skill:

```bash
npx skills add alanjgo/product-skills --skill ab-test --yes
npx skills add alanjgo/product-skills --skill business-opportunity --yes
npx skills add alanjgo/product-skills --skill data --yes
npx skills add alanjgo/product-skills --skill documentation --yes
npx skills add alanjgo/product-skills --skill point-etape --yes
npx skills add alanjgo/product-skills --skill prd --yes
npx skills add alanjgo/product-skills --skill stress-test --yes
npx skills add alanjgo/product-skills --skill weekly-update --yes
```

Install for Claude Code specifically:

```bash
npx skills add alanjgo/product-skills --agent claude-code --skill '*' --yes
```

Use a skill once without installing it:

```bash
npx skills use alanjgo/product-skills@ab-test
npx skills use alanjgo/product-skills@business-opportunity
npx skills use alanjgo/product-skills@data
npx skills use alanjgo/product-skills@documentation
npx skills use alanjgo/product-skills@point-etape
npx skills use alanjgo/product-skills@prd
npx skills use alanjgo/product-skills@stress-test
npx skills use alanjgo/product-skills@weekly-update
```

## Usage Examples

Invoke a skill by name using your agent's preferred syntax. If your agent supports `$skill-name`, use:

```text
Use $ab-test to analyze this experiment:
- Variant A conversion: 8.2%
- Variant B conversion: 8.9%
- Sample size: 18,000 users per variant
- Guardrail: refund rate unchanged
Recommend whether we should roll out, roll back, or retest.
```

```text
Use $stress-test to challenge this roadmap proposal:
We want to build a new partner-facing dashboard so hotels can manage their packages without asking Ops.
Tell me what a CEO/CPO would challenge and rewrite it so it is easier to defend.
```

## Skill Details

### `ab-test`

Use this skill when you have experiment metrics, screenshots, or a written summary and need a decision-oriented readout. The skill checks result integrity, segment effects, business impact, guardrails, and the next best action.

Expected output includes:

- Summary
- Questions to answer
- Segment read
- Business calculations
- Actionable learnings
- Recommendation
- Next iterations

### `business-opportunity`

Use this skill to evaluate, compare, or document new features, growth ideas, segment expansions, or marketplace opportunities. It centers the analysis on GMV levers, assumptions, sizing, and follow-up experiments or data pulls.

Expected output includes:

- Opportunity assessment
- Objective
- Key results
- Customer problem
- Target market

### `data`

Use this skill to draft readable PostgreSQL queries for Staycation marketplace questions. It asks the agent to check schema sources before choosing tables, joins, filters, grain, and output shape.

Expected output includes:

- Question recap
- Assumptions
- SQL query
- Validation notes

### `documentation`

Use this skill to document a feature, product area, internal process, or functional behavior in concise Markdown for mixed business, marketing, product, and technical readers.

Expected output includes:

- Objective
- How it works
- Use cases
- Business or product impact
- Frequently asked questions

### `point-etape`

Use this skill to turn rough French meeting notes, transcripts, bullets, or context into a clear checkpoint with objective, context, scope, recommendation, and next steps.

Expected output includes:

- Meeting objective
- Context and importance
- Scope
- Recommendation
- Next steps

### `prd`

Use this skill to create, restructure, or sharpen a concise Product Requirement Document from notes, ideas, Slack threads, or existing drafts.

Expected output includes:

- User message
- Problem
- Solution
- Scenario
- Milestone
- Metrics

### `stress-test`

Use this skill when a concept, PRD, launch plan, or strategy recommendation needs sharper executive scrutiny. The skill separates weak problem framing, weak solution logic, and weak narrative, then rewrites the idea in a stronger form.

Expected output includes:

- Executive reaction
- What leadership would challenge
- Verdict
- Sharpened version of the concept

### `weekly-update`

Use this skill to prepare a concise French weekly update for active PELU projects, focusing on what happened this week and what is planned next week.

Expected output includes:

- This week
- Next week

## Repository Structure

```text
.
├── ab-test/
│   └── SKILL.md
├── business-opportunity/
│   └── SKILL.md
├── data/
│   ├── SKILL.md
│   └── references/
│       └── schema-sources.md
├── documentation/
│   └── SKILL.md
├── point-etape/
│   └── SKILL.md
├── prd/
│   └── SKILL.md
├── stress-test/
│   └── SKILL.md
├── weekly-update/
│   └── SKILL.md
├── LICENSE
└── README.md
```

## Validation

Validate the skills with the official reference validator:

```bash
python -m pip install "git+https://github.com/agentskills/agentskills.git#subdirectory=skills-ref"
skills-ref validate ./ab-test
skills-ref validate ./business-opportunity
skills-ref validate ./data
skills-ref validate ./documentation
skills-ref validate ./point-etape
skills-ref validate ./prd
skills-ref validate ./stress-test
skills-ref validate ./weekly-update
```

## License

MIT. See [LICENSE](LICENSE).
