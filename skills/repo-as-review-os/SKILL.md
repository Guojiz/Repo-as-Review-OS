---
name: repo-as-review-os
description: Route GitLearnOS work to the smallest relevant setup, learning-session, source, model, review, or maintenance workflow. Use for a lightweight GitHub-native tutoring repository operated by one capable AI agent.
---

# GitLearnOS Router

## Product boundary

GitLearnOS is a portable tutoring toolkit for an existing AI runtime. It is capability-benchmarked against DeepTutor's source-grounded, personalized, closed learning loop, but it does not reproduce DeepTutor's application, RAG stack, multi-agent runtime, or UI.

Use one main agent and one target learning repository by default.

## Start with minimum context

Before routing:

1. distinguish the template repository from the target learning repository;
2. detect actual read/write/source permissions;
3. read target `dashboard.md`, active goal, and `learner-profile.md`;
4. load only the files needed for the current task.

Do not read every GitLearnOS document or every subskill before acting.

## Route one task

### Setup or migration

Use `skills/repo-as-review-os-setup/SKILL.md` when the target learning state is missing or must be migrated.

### Live learning

Use `skills/repo-as-review-os-session/SKILL.md` when the learner asks to learn, continue, practise, understand, be quizzed, or decide what to study now.

This is the default tutoring path. Do not route a real learning request to file maintenance alone.

### Source handling

Use `skills/repo-as-review-os-source/SKILL.md` when material, a reference, a mistake, or an incomplete recollection must be recorded honestly.

### Reusable model

Use `skills/repo-as-review-os-model/SKILL.md` when an event should become a recognition cue, method, concept, comparison dimension, or transferable pattern.

### Review

Use `skills/repo-as-review-os-review/SKILL.md` when due items need prompts, scoring, scheduling, or review-result writeback.

### Maintenance

Use `skills/repo-as-review-os-maintenance/SKILL.md` for stale dashboards, broken links, unsupported mastery claims, missing evidence, duplication, or handoff repair.

## Tutoring kernel

All learning-facing paths preserve this loop:

```text
goal
→ grounded source or prior model
→ learner attempt
→ diagnosed gap
→ adaptive support
→ independent or transfer check
→ evidence score 0–3
→ selective writeback
→ next review/action
```

## Universal rules

1. Never write personal state into the template repository.
2. Never treat a summary as a full source.
3. Never infer mastery from exposure, completion, or self-report alone.
4. Separate observed evidence from hypotheses about the learner.
5. Write back only state with future learning value.
6. Keep the dashboard as a linked view, not a duplicate source of truth.
7. Use current tools directly when authorized; manual copy-and-paste is a fallback.
8. Ask before destructive, visibility, privacy, secret, or license changes.
9. Report every changed file and the learning evidence, if any.

## Output

```text
Mode used:

Changed files:
- path: reason

Learning evidence:
- score and observation, or not assessed

Still missing:
- source, attempt, or decision

Next action:
- one concrete step
```
