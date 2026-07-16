---
name: repo-as-review-os
description: Route GitLearnOS work for a learner-owned repository to the smallest organization, question-generation, setup, tutoring-session, source, model, review, or maintenance workflow. Use when one capable main agent should organize learning from any channel, generate targeted questions, and automate safe writeback.
---

# GitLearnOS Router

## Product boundary

Treat GitLearnOS as a learner-owned control layer:

```text
organize automatically
→ generate targeted questions
→ write back under learner policy
```

Learning may happen with teachers, class, paper, platforms, peers, or AI. Use one capable main agent. Do not require a multi-agent runtime, app, database, RAG stack, or background service.

## Read minimum context

1. distinguish template and target repositories;
2. detect actual read, write, source, and scheduling capability;
3. read target `learning-policy.md` when present;
4. infer the subject from explicit language, material, linked goals, and existing paths;
5. read root `dashboard.md`, the active `subjects/<subject>/` goal, and only related files;
6. load one primary subskill, plus one helper only when necessary.

Keep shared policy, learner profile, and cross-subject dashboard at the repository root. Route subject-specific state under `subjects/<subject>/`. Ask only when ambiguity would cause a wrong write; honor a learner correction immediately. Never require the learner to choose a path or create empty subject trees.

## Route by intent

### Setup or migration

Use `skills/repo-as-review-os-setup/SKILL.md` when the target state is missing or must be migrated.

### Organize and reconcile

Use `skills/repo-as-review-os-organize/SKILL.md` for notes, mistakes, teacher feedback, practice-platform results, duplicate input, external resolution, or cross-channel state sync.

This is the default path for “record,” “organize,” “my teacher said,” “I solved this elsewhere,” and “update my repository.”

### Generate questions

Use `skills/repo-as-review-os-question/SKILL.md` for diagnostic, practice, variation, transfer, review, or help-seeking questions.

This includes both questions for the learner and a context-rich pack to take to a teacher, peer, or another agent.

### Live AI tutoring

Use `skills/repo-as-review-os-session/SKILL.md` only when the learner wants AI explanation, guided practice, or testing now.

Do not route note organization, external feedback, or teacher preparation into tutoring by default.

### Source handling

Use `skills/repo-as-review-os-source/SKILL.md` when provenance, access, completeness, privacy, or an unavailable original needs careful handling.

### Reusable model

Use `skills/repo-as-review-os-model/SKILL.md` when durable understanding should become a cue, method, concept, comparison, or transferable pattern.

### Review and scheduling

Use `skills/repo-as-review-os-review/SKILL.md` when an existing question set needs administration, scoring, interval calculation, or result writeback.

### Maintenance and undo

Use `skills/repo-as-review-os-maintenance/SKILL.md` for stale dashboards, broken links, unsupported claims, duplication, policy drift, handoff repair, or safe undo.

## Shared automation contract

Read `learning-policy.md`. Default to `safe-auto` if absent:

- directly perform safe, low-risk, reversible organization, question, link, scheduling, and dashboard updates;
- report all writes afterward;
- ask before deletion, broad restructuring, publication, sensitive identity, policy changes, secrets, or license changes;
- honor one-event overrides such as “record only,” “no review,” “do not store,” and “preview first”;
- make repeated input idempotent;
- make one learning event one atomic, reversible update when supported.

Distinguish immediate automation, on-handoff checks, and real scheduled background automation. Never claim the third without creating it through an actual scheduler.

## Shared evidence contract

- external resolution and independent mastery are separate;
- label evidence `reported`, `source-supported`, or `demonstrated`;
- do not infer score 3 from exposure, completion, or self-report;
- generated questions remain planned until attempted;
- preserve contradictory evidence and adjust confidence.

## Receipt

```text
Mode:
Subject path:
Organized:
Questions:
Changed files:
Evidence:
Actual automation:
Next action:
Undo:
```
