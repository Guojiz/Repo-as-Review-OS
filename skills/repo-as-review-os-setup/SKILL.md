---
name: repo-as-review-os-setup
description: Create or migrate the minimum learner-owned GitLearnOS state while preserving existing files, configuring automation and privacy policy, and preparing the first useful organization, question-generation, or learning action for one main agent.
---

# GitLearnOS Setup

## Boundary

Treat `Guojiz/Repo-as-Review-OS` as the template and the learner's repository as the target. Never place personal state in the template.

## Capability-first setup

1. identify the target;
2. test actual read, write, source, and scheduling capability;
3. inspect existing files;
4. ask only for information tools cannot obtain;
5. preserve existing work.

## Minimum state

Create only what the first goal or input needs:

```text
AGENTS.md or AGENTS.zh-CN.md
learning-policy.md
dashboard.md
learner-profile.md
goals/main-goal.md
```

Then create real state under only the required folders:

```text
inbox/
sources/
models/
knowledge-gaps/
handoffs/
reviews/
sessions/
archive/
```

Do not add empty scaffolding.

## Setup order

1. capture the first goal or input;
2. establish `learning-policy.md` with `safe-auto` unless the learner requests preview/manual;
3. create minimal profile and dashboard with one next action;
4. organize the first real input or gap;
5. generate questions only when useful or requested;
6. run an AI session only when the learner requests it;
7. verify that the agent can identify state, act, write, report, and honor undo boundaries.

## Migration

- inventory before moving;
- map existing notes to goals, sources, models, gaps, or archive;
- preserve paths that support learner habits or links;
- ask before broad moves or overwrites;
- migrate one active learning path first.

## Output

```text
Target:
Capabilities:
Policy:
Changed files:
First organized path:
Questions prepared:
Still missing:
Next action:
```
