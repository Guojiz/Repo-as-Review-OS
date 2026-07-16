---
name: repo-as-review-os-review
description: Administer, score, schedule, and write back GitLearnOS reviews from existing targeted question sets. Use when the learner answers planned questions, a due review must run, results need observable 0–3 scoring, or the next interval and linked learner state must be updated.
---

# GitLearnOS Review

## Boundary

Use `repo-as-review-os-question` to generate a new targeted set. Use this skill to administer, score, and update the result.

## Administer

Resolve the subject from the existing review path, then read the linked goal, source/model, gap, question purpose, answer key or rubric, and recent results inside that subject. Do not reveal answers before the learner attempts unless requested.

Record:

- learner response summary;
- independent portion;
- correctness and error type;
- support level;
- transfer result when required;
- observable score;
- next review date or no-review decision.

| Score | Evidence | Default interval |
|---|---|---|
| 0 | incorrect after substantial support | 1 day |
| 1 | correct with major hints or imitation | 2 days |
| 2 | correct with a minor hint or small execution error | 4 days |
| 3 | independently correct; transfer succeeds when required | 7 days |

After two consecutive score-3 reviews, double the prior interval up to 30 days.

## Writeback

Under policy:

1. update the review record;
2. update mastery evidence in the linked gap without overwriting resolution provenance;
3. update model review fields when present;
4. refresh dashboard;
5. update learner profile only for repeated durable patterns;
6. create real scheduled automation only when a scheduler is available.

A generated but unattempted set remains `planned`. A teacher's resolution may change gap resolution but does not create a score.

## Output

```text
Review status:
Subject path:
Evidence type: demonstrated / not-assessed
Score:
Support:
Files updated:
Next review or check-on-handoff:
Next action:
```
