---
name: repo-as-review-os-setup
description: Create or migrate the minimum viable GitLearnOS state in a target repository while preserving existing files, adapting to the current tool-capable runtime, and preparing the first evidence-based learning session.
---

# GitLearnOS Setup

## First rule

Treat `Guojiz/Repo-as-Review-OS` as the template and the user's chosen repository as the target. Never place personal learning data in the template.

## Capability-first setup

1. identify the target repository;
2. test actual read and write access;
3. inspect existing target files;
4. ask only for information that tools cannot obtain;
5. preserve existing work and avoid broad replacement.

In a tool-capable workspace, perform safe setup directly. In a read-only chat, produce a writeback package and label it pending.

## Minimum viable state

Create only what the first goal needs:

```text
AGENTS.md or AGENTS.zh-CN.md
dashboard.md
learner-profile.md
goals/main-goal.md
```

Then create the first relevant file under one or more of:

```text
inbox/
sources/
models/
knowledge-gaps/
reviews/
sessions/
archive/
```

Git does not preserve empty directories. Do not add `.gitkeep` files merely to make the tree look complete unless the user wants a fixed scaffold.

## Setup order

1. Confirm or infer the first learning goal from the user's request.
2. Create the goal and a minimal learner profile; mark unknown fields as unknown.
3. Create a dashboard with one next action, not a fictional task list.
4. Copy only the relevant templates or link back to the template repository.
5. Add the canonical agent rules.
6. Run or prepare the first short learning session.
7. Verify that the agent can answer: active goal, due item, evidence, next action, changed files.

Do not copy all public docs, demos, platform guides, or every skill into a personal target repository by default.

## Existing repository migration

- inventory before moving files;
- map existing notes to goals, sources, models, gaps, or archive;
- preserve original paths when links or user habits depend on them;
- ask before large moves, merges, or overwrites;
- migrate one active learning path first, then expand.

## Output

```text
Target repository:
Capability verified:

Changed files:
- path: reason

First learning path:
- goal → source/gap/model/review

Still missing:
- only real blockers

Next action:
- first session
```
