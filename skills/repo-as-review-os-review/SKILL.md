---
name: repo-as-review-os-review
description: Use when generating review sets, practice prompts, mini tests, spaced repetition tasks, or daily learning plans from goals, models, weak points, and dashboard state in a Repo as Review OS repository.
---

# Repo as Review OS Review Skill

## Purpose

Use this skill to generate review work from the user's current learning state.

The goal is not to recommend random practice. The goal is to generate targeted review from the user's own goals, sources, models, weak points, and review dates.

## When to use

Use when the user asks for:

- a review set;
- a practice set;
- a mini test;
- today's study plan;
- spaced repetition tasks;
- a weak-point drill;
- a custom paper or question set;
- a review based on the repository.

## Review workflow

```text
read dashboard
→ read active goal
→ find due models
→ find weak points
→ choose review format
→ generate review prompts
→ write review set
→ update dashboard or model review fields
```

## Review set should include

```text
status: generated-review
goal link
source models
why this was generated
review prompts or tasks
writeback instructions
next review action
```

## Review quality rules

A review set should be:

- short enough to complete;
- tied to existing models;
- based on weak points;
- clear about what to write back;
- honest about missing sources.

Do not create a huge random worksheet unless the user explicitly asks for it.

## Example requests

```text
Generate a 30-minute review set from my weak points.
```

```text
Make a mini test from the models due today.
```

```text
Give me three prompts to check whether I still remember this concept.
```

## Output standard

```text
Changed files:
- review path: what was generated
- dashboard/model path: what was updated

Still missing:
- missing source or model

Next action:
- complete review / update memory status / schedule next review
```
