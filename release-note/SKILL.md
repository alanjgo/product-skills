---
name: release-note
description: Write internal Slack announcements in English for launches, fastlane changes, hotfixes and experiments. Use when a new feature ships, a fastlane change or bugfix goes live, an A/B test starts or ends, or a rollout decision needs to be communicated internally.
---

# Internal Release Notes

Draft short Slack messages for `#release-note` that a non-tech reader can understand in under 30 seconds: why it matters, what changed, and whether it concerns them.

The audience is the whole company, not the Product team. Three problems the format exists to fix:
- messages that are unreadable for anyone outside Product
- readers who cannot tell whether a change concerns them
- a high volume of messages every day

So: no internal jargon, no bare ticket references, no unexplained acronyms. Say who is concerned, every time.

## Who posts what

| Type | Written by | Audience |
| --- | --- | --- |
| 🚀 New feature released | PM | Whole company |
| 🛣️ Fastlane Feature | PM (at spec time, in the Linear ticket) | Whole company |
| 🧪 A/B test starting / ending | PM | Whole company |
| 🚒 Hotfix/Bugfix shipped | Developer | Mostly Product team |

PM-authored messages carry the full context, the why, and screenshots. Dev-authored bugfix messages are lighter.

**Fastlane workflow:** the PM writes the release note during the spec, right after co-conception, and stores it in the Linear ticket. At deploy, the dev copy-pastes it as-is — publication must never wait on the PM's availability. When drafting a fastlane note, produce a message that is ready to paste into the ticket with nothing left to fill in.

## Workflow

1. Identify the type: new feature, fastlane, hotfix/bugfix, A/B test start, A/B test result. (Rollout decisions use the variant at the end.)
2. Gather context, then write the message with the matching template.
3. Only include a section when you actually have the information. Never invent numbers, dates, owners, or metrics.
4. List any missing element the user should fill in before posting — screenshots especially.

## Context gathering

Use the associated Notion docs, Linear tickets, or user-provided context to recover:

- why the work was done, and the user benefit
- what changed
- who is concerned
- platform and rollout scope
- experiment results or decision

If a key element is missing, ask once rather than guessing.

## 🚀 New feature released

```md
*🚀 New feature released: [Feature name]*

*Context*
- Why this feature: user benefit, problem it solves
- OKR it contributes to (optional)
- Who is concerned: which users have access

*Before* (optional)
- How it worked before

*What changes now*
- What users see and where
- How to use it
- Screenshot and/or video
```

## 🛣️ Fastlane Feature

Same structure, lighter. Written by the PM at spec time and pasted into the Linear ticket for the dev to publish at deploy.

```md
*🛣️ Fastlane Feature: [Change name] 🛣️*

*Context*
- Why this change, and who is concerned

*Before* (optional)
- How it worked before

*What changes now*
- What users see and where
- Screenshot if relevant
```

## 🚒 Hotfix/Bugfix shipped

Written by developers. Keep it short — context in one line is enough.

```md
*🚒 Hotfix/Bugfix shipped 🚒*

*Context*
- What was broken, for whom, since when

*Before* (optional)
- What users were experiencing

*What changes now*
- The fixed behaviour, and where to check it
```

## 🧪 A/B test starting

```md
*🧪 A/B test starting: [Test name]*

*Context*
- Hypothesis and the problem behind it
- Who is in the test: platform, segment, traffic split

*What changes for the variant*
- What the variant sees, and where

*How we will decide*
- Primary metric, guardrails
- Expected end date
- Link: [Notion / Linear]
```

## 🧪 A/B test ending

```md
*🧪 A/B test ending: [Test name]*

*What we tested*
- Hypothesis in one line, population, duration

*Results*
- Primary metric: effect, significance
- Guardrails and notable segments

*What we learned*
- The takeaway, including when the result is flat or negative

*Next step*
- Ship, iterate, or stop
```

### Rollout decision (variant)

Not one of the four official types — use it when a decision needs its own message rather than a line in the test result.

```md
*✅ [Feature name] — rollout decision*

*Decision*
- What we are rolling out, to whom, from when

*Why*
- Evidence behind the decision in one or two lines

*What changes for users*
- Concrete impact

*What this means for teams*
- Anything Ops, Care, or Sales should know
```

## In the thread, not the message

Keep the main message scannable. Everything below goes in the thread:

- Data changes: new tables, new fields, tracking updates
- Links to the Notion doc or Linear ticket
- Tagging the teams concerned, via Slack user groups (`@product`, `@am`, `@bd`, `@care`, `@merch`, `@data`) rather than individuals — optional, and only when the change actually concerns them

## Style

- Write in English. (The source guidelines label the first section *Contexte*; either spelling is fine, stay consistent within a message.)
- One lead emoji in the bold title line, matching the type. No extra emoji in the body.
- Short bullets, one idea per line, bold section labels. Slack formatting (`*bold*`), never Markdown headings. No em dashes.
- User impact before technical detail. Explain any term a non-Product reader would not know.
- Friendly and positive without sounding inflated. No hype adjectives, no exclamation stacking.
- Readable in under 30 seconds.
- Report negative or flat experiment results as plainly as positive ones.
