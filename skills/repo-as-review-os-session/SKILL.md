---
name: repo-as-review-os-session
description: Run an optional evidence-based live AI learning session in GitLearnOS. Use when the learner explicitly wants the AI to explain, guide practice, quiz, or diagnose now; do not use by default for note organization, teacher feedback, external resolution, or preparation for human help.
---

# GitLearnOS Live AI Session

## Boundary

Use this only for live AI teaching. Use `repo-as-review-os-organize` for capture and external feedback, and `repo-as-review-os-question` for standalone question generation or teacher handoffs.

## Read

Resolve the subject, then read its active goal, the relevant root learner-profile section, one subject-local gap or due item, and the minimum source/model. Respect root `learning-policy.md`.

## Loop

1. Set one observable objective.
2. Ask for recall, prediction, explanation, solution, comparison, or application before giving the full answer, unless the learner explicitly asks for direct reference.
3. Diagnose prerequisite, recognition, method, execution, explanation, transfer, or uncertain.
4. Give the minimum effective support: cue → focused question → partial example → worked step → full explanation.
5. Verify with a fresh task; call `repo-as-review-os-question` when a designed variation or transfer set is needed.
6. Score demonstrated evidence 0–3 through `repo-as-review-os-review`.
7. Write back only durable change and return a receipt.

Do not reteach a problem merely because it was resolved with a human teacher. If external feedback is the current input, organize it first and ask whether the learner wants explanation only if that remains useful.

## Stop

Stop or narrow when the learner is fatigued, the source is unavailable, the goal changed, the task is too large, or further questioning no longer adds value.

## Output

```text
Objective:
Subject path:
Questions used:
Evidence score:
Support:
Files updated:
Next action:
```
