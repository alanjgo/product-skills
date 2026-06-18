---
name: ab-test
description: Analyze A/B test results like a senior product manager. Use when the user shares experiment metrics, screenshots, or a results summary and wants insights, watchouts, segment analysis, a business impact estimate, or a recommendation to roll out, roll back, or run another test.
---

# A/B Test Analysis

Turn experiment results into a product decision, not just a scorecard.

## Workflow

1. Frame the experiment: identify the variants being compared, the hypothesis, the primary metric, secondary metrics, guardrail metrics, targeting, split, sample size, duration, and obvious watchouts.
2. Check result integrity before interpreting the results: flag risks such as too small a sample size, too short a duration, sample ratio mismatch, ambiguous tracking, exposure issues, or users switching variants.
3. State which variant performs best on the primary metric, what happens on secondary metrics, and whether the result is significant, mixed, or inconclusive.
4. Look for heterogeneous effects: determine whether the tested variant affects certain user segments differently, and name the segments to inspect when relevant.
5. List useful business calculations when the data allows it, for example annual revenue impact, incremental bookings, impact per exposed user, opportunity by segment, or the potential cost of a poor decision.
6. List the precise questions the analysis must answer, especially when the user needs to structure the readout rather than only interpret a final result.
7. Translate results into product or behavioral learnings instead of repeating the numbers.
8. Recommend a single next step: roll out, roll back, or run another test.
9. Anticipate what comes next based on the result:
   * Positive and significant: specify whether a gradual rollout is needed, which user groups to include first, which guardrail metrics to monitor, and whether technical cleanup such as removing the feature flag should be planned.
   * Negative and significant: explain what still worked well, the learnings, what could have been done differently, and what should be adjusted before another test.
   * Not significant: decide whether to extend, retest, or stop; clarify time and resource constraints, what can be changed, what must remain stable, and how to capitalize on the learnings if no new test is launched.
10. Propose 1 to 3 concrete iterations, each tied to a hypothesis.

## Expected Output

Use this structure unless the user asks for another format.

### Summary

* Write 2 to 4 bullets with the main takeaways.
* Highlight the winning variant, or the absence of a clear winner.
* Mention visible watchouts such as low sample size, short duration, segment imbalance, sample ratio mismatch, or tracking risk.

### Questions to Answer

* List 3 to 6 precise questions the analysis must answer.
* Favor decision-oriented questions, for example:

  * Which variant should be rolled out, if any?
  * Do some segments react differently enough to change the recommendation or rollout order?
  * Is the observed lift large enough to matter at the business level?
  * Is any guardrail metric degrading enough to block the rollout?
  * If the result is inconclusive, is another test really worth the investment?

### Segment Read

* List the relevant user cuts to inspect when useful.
* Prioritize segments that could change the decision rather than running an exhaustive analysis.
* Explicitly state whether a segmented read could change the rollout, rollback, or retest plan.

### Business Calculations

* List the quick calculations that would be useful to run.
* Quantify only when the input data is available.
* If inputs are missing, state exactly which ones are needed.

### Actionable Learnings

* Write 3 to 5 bullets that translate the result into behavioral or product learnings.
* When possible, connect the result to a broader implication for the product or business.

### Recommendation

* State roll out, roll back, or run another test in 1 to 2 sentences.
* Explain why this is the best next step.
* If a rollout is recommended, add the guardrail metrics to monitor.
* Explicitly adapt the recommendation to one of the three cases: positive significant, negative significant, or not significant.

### Next Iterations

1. Suggest 2 to 3 experiments or product adjustments.
2. Add a short hypothesis and expected impact for each.

## Style

* Be concise and decision-oriented.
* Avoid false precision.
* Make assumptions and missing input data explicit.
* Prefer decision-useful segmentation over exhaustive analysis.
* If the result is not significant, do not force a winner.