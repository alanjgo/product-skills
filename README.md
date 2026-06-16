# Skills for Product Managers

Two open-source agent skills for product decision work:

- `ab-test`: analyze A/B test results as a senior product manager and turn experiment metrics into a rollout, rollback, or retest decision.
- `stress-test`: pressure-test a product concept, spec, launch plan, roadmap proposal, or recommendation through a Staycation CEO/CPO lens.

Each skill is a self-contained folder with:

- `SKILL.md`: the agent instructions and trigger metadata.

The repository follows the [Agent Skills specification](https://agentskills.io/specification): each skill directory contains a `SKILL.md` file with YAML frontmatter and Markdown instructions. No runtime-specific configuration is required.

## Installation

Clone the repository:

```bash
git clone https://github.com/alanjgo/staycation-product-skills.git
```

Then install each skill according to your agent runtime's convention. The portable source of truth is each `SKILL.md` file:

- `staycation-product-skills/ab-test/SKILL.md`
- `staycation-product-skills/stress-test/SKILL.md`

For agents that support local skill folders, copy or symlink the two folders into that agent's skills directory:

```bash
mkdir -p ~/.agent/skills
cp -R staycation-product-skills/ab-test ~/.agent/skills/
cp -R staycation-product-skills/stress-test ~/.agent/skills/
```

If your agent does not have a skill-folder system, paste or reference the relevant `SKILL.md` content in the agent's system instructions, project instructions, or custom prompt library.

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

### `stress-test`

Use this skill when a concept, PRD, launch plan, or strategy recommendation needs sharper executive scrutiny. The skill separates weak problem framing, weak solution logic, and weak narrative, then rewrites the idea in a stronger form.

Expected output includes:

- Executive reaction
- What leadership would challenge
- Verdict
- Sharpened version of the concept

## Repository Structure

```text
.
├── ab-test/
│   └── SKILL.md
├── stress-test/
│   └── SKILL.md
├── LICENSE
└── README.md
```

## Validation

Validate both skills with the official reference validator:

```bash
python -m pip install "git+https://github.com/agentskills/agentskills.git#subdirectory=skills-ref"
skills-ref validate ./ab-test
skills-ref validate ./stress-test
```

## License

MIT. See [LICENSE](LICENSE).
