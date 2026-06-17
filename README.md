# Skills for Product Managers

Open-source agent skills for product decision work:

- `ab-test`: analyze A/B test results as a senior product manager and turn experiment metrics into a rollout, rollback, or retest decision.
- `business-opportunity`: size and assess business opportunities through GMV levers.
- `data`: draft readable PostgreSQL queries for data questions.
- `documentation`: write concise product documentation for mixed product, business, marketing, and tech audiences.
- `point-etape`: turn rough meeting notes into a decision-ready checkpoint update.
- `prd`: draft or improve concise, outcome-driven PRDs.
- `stress-test`: pressure-test a product concept, spec, launch plan, roadmap proposal, or recommendation through a CEO/CPO lens.
- `weekly-update`: prepare concise weekly French updates for squad projects.

Each skill is a self-contained folder with:

- `SKILL.md`: the agent instructions and trigger metadata.

The repository follows the [Agent Skills specification](https://agentskills.io/specification): each skill directory contains a `SKILL.md` file with YAML frontmatter and Markdown instructions. No runtime-specific configuration is required.

## Installation

Clone the repository:

```bash
git clone https://github.com/alanjgo/product-skills.git
```

### Install with `npx skills`

You can also install directly from this public GitHub repository with the `skills` CLI.

List the skills available in the repository:

```bash
npx skills add alanjgo/product-skills --list
```

Install all skills:

```bash
npx skills add alanjgo/product-skills --skill '*' --yes
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
