---
name: repo-as-review-os-review
description: Generate, administer, score, and schedule GitLearnOS reviews from active goals, evidence-backed knowledge gaps, models, and due dates; use observable 0–3 evidence rather than completion or self-report.
---

# GitLearnOS Review

## Two distinct operations

### Generate

Create a small review set from:

```text
active goal
+ due items
+ evidence-backed gaps
+ relevant models and sources
+ recent results
```

Prefer 1–5 focused prompts. Include recall, application, or transfer only as the goal requires. Do not reveal answers before the learner attempts the task.

### Administer and score

Record:

- learner response summary;
- independence/hint level;
- correctness and error type;
- transfer result when required;
- score 0–3;
- next review date;
- files that must change.

| Score | Evidence | Default interval |
|---|---|---|
| 0 | incorrect after substantial support | 1 day |
| 1 | correct with major hints or imitation | 2 days |
| 2 | correct with a minor hint or small execution error | 4 days |
| 3 | independently correct; transfer succeeds when required | 7 days |

After two consecutive score-3 reviews, double the prior interval up to 30 days.

## Writeback

After scoring:

1. update the review record;
2. update the linked gap status and evidence;
3. update model review fields if present;
4. update the dashboard;
5. update learner profile only for repeated or durable patterns.

A generated but unattempted review must remain `planned`, not `completed` or `mastered`.

## Output

```text
Review status: planned / attempted / scored
Evidence score: 0 / 1 / 2 / 3 / not assessed
Files updated:
Next review:
Next action:
```
