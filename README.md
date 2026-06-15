# Staycation Product Skills

Two open-source Codex skills for product decision work:

- `ab-test`: analyze A/B test results as a senior product manager and turn experiment metrics into a rollout, rollback, or retest decision.
- `stress-test`: pressure-test a product concept, spec, launch plan, roadmap proposal, or recommendation through a Staycation CEO/CPO lens.

Each skill is a self-contained folder with:

- `SKILL.md`: the agent instructions and trigger metadata.
- `agents/openai.yaml`: optional Codex UI metadata for display name, short description, and default prompt.

## Installation

Clone the repository, then copy the skills into your Codex skills directory:

```bash
git clone https://github.com/alanjgo/staycation-product-skills.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R staycation-product-skills/ab-test "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R staycation-product-skills/stress-test "${CODEX_HOME:-$HOME/.codex}/skills/"
```

If you prefer to keep the repository as the source of truth, symlink the folders instead:

```bash
git clone https://github.com/alanjgo/staycation-product-skills.git ~/Code/staycation-product-skills
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
ln -sfn ~/Code/staycation-product-skills/ab-test "${CODEX_HOME:-$HOME/.codex}/skills/ab-test"
ln -sfn ~/Code/staycation-product-skills/stress-test "${CODEX_HOME:-$HOME/.codex}/skills/stress-test"
```

Restart Codex after installation so the skills are discovered.

## Usage Examples

Invoke a skill explicitly with `$skill-name`.

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
│   ├── SKILL.md
│   └── agents/openai.yaml
├── stress-test/
│   ├── SKILL.md
│   └── agents/openai.yaml
├── LICENSE
└── README.md
```

## License

MIT. See [LICENSE](LICENSE).
