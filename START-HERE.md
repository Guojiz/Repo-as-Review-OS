# Start Here: Agent Handoff

GitLearnOS is a learner-owned control layer. One main agent organizes automatically, generates targeted questions, and performs safe writeback; live AI tutoring is optional. Do not preload the template repository.

## 1. Identify two repositories

```text
template: Guojiz/GitLearnOS
target learning repository: <learner repository or unknown>
```

Never place personal learning state in the template. If writeback is required and the target is unknown, ask only for the target.

## 2. Detect actual capability

Internally confirm:

```text
template read:
target read:
target write:
connected sources:
skill support:
real scheduler:
steps the learner must perform:
```

Do not make the learner repeat work the current runtime can safely perform. A prompt is not automation and a plan is not writeback.

## 3. Resolve the subject folder

Infer the subject from the current material, explicit user language, linked goal, and existing paths. Subject-specific state belongs under `subjects/<subject>/`. Ask one short question only when ambiguity would cause an incorrect write. A user correction always overrides inferred routing.

Keep `learning-policy.md`, `learner-profile.md`, and the cross-subject `dashboard.md` at the repository root. Do not create empty subject folders.

## 4. Read minimum state

Initially read only:

1. this file;
2. `AGENTS.md`;
3. target `learning-policy.md` when present;
4. root `dashboard.md` and the active subject entry;
5. the active goal and minimum related files inside `subjects/<subject>/`.

## 5. Identify intent

- **setup:** bootstrap or migrate;
- **organize:** notes, mistakes, teacher feedback, platform results, deduplication, and state sync;
- **question:** diagnostic, practice, variation, transfer, review, or teacher-facing question pack;
- **session:** the learner explicitly wants AI tutoring now;
- **review:** existing questions need administration, scoring, scheduling, or writeback;
- **source / model:** provenance or reusable understanding;
- **maintenance:** stale, contradictory, duplicate, broken, or undo work.

Use `skills/repo-as-review-os/SKILL.md` when skills are supported. Do not route all learning requests to session.

## 6. Organize and write back

```text
capture input
→ mark channel, provenance, and privacy
→ resolve subjects/<subject>/
→ link goal, gap, and existing state
→ deduplicate
→ organize, question, handoff, verify, or record only
→ write under learning-policy
→ refresh dashboard
→ return a receipt
```

Default to `safe-auto`: perform safe, low-risk, reversible learning-state changes and report them; ask before deletion, publication, sensitive identity, broad restructuring, or policy changes.

## 7. Handle external learning correctly

Teachers, class, tutoring, paper, and other platforms are first-class sources.

- “prepare for my teacher” → create a `subjects/<subject>/handoffs/` question pack and mark waiting feedback;
- “my teacher resolved it” → update resolution, reconcile feedback, retire obsolete tasks;
- “these are my notes” → record provenance and extract only useful models;
- “do not test me” → honor the choice;
- “undo that” → safely reverse the latest atomic learning update when supported.

External resolution is not independent mastery, but it must not trigger forced AI reteaching.

## 8. Generate questions correctly

Connect questions to a goal, source or model, knowledge gap, and recent performance. Record purpose, difficulty, time, answer or rubric, and novelty. Never verify with the exact demonstrated item.

## 9. Finish clearly

```text
Mode:
Subject path:
Organized:
Questions:
Changed files:
Evidence type:
Actual automation:
Next action:
Undo:
```
