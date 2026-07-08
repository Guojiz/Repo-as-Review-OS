# Operating Model

GitLearnOS is a lightweight learning-trace operating system for AI-assisted study, built on GitHub.

It is not just a review template. It is a way for one AI tool to help a user learn, remember, reorganize, and generate new understanding from old material.

## Core thesis

Use GitHub as the writable learning timeline.

Use one target repository for the user's learning state.

Use one main AI tool as the maintainer.

Use goals to decide what matters.

Use files and folders to express state.

Use knowledge gaps to decide what should be practiced next.

Use spaced repetition to prevent forgetting.

Use automation to organize, critique, revise, and generate practice.

## Template vs target repository

```text
Repo-as-Review-OS repository
→ template repository
→ method, docs, skills, examples, rules

User target repository
→ personal GitLearnOS repository
→ goals, learner profile, sources, models, knowledge gaps, reviews, dashboard
```

The AI should read this repository as the template and write learning state only into the user's target repository.

## The order AI should follow

When an AI tool receives this repository, it should follow this order:

1. Identify its runtime, memory capability, file access, and permission level.
2. Separate the template repository from the target learning repository.
3. Read the user's goal.
4. Check the target repository structure.
5. Find active sources, models, learner profile, and knowledge gaps.
6. Decide what should be split, merged, rewritten, reviewed, generated, or archived.
7. Update files in the target repository.
8. Suggest native-memory updates only for stable preferences or repeated patterns.
9. Schedule review if needed.
10. Report every change.

## What the repository is for

The repository should not collect everything.

It should transform material:

```text
raw material
→ source record
→ extracted item
→ reusable model
→ knowledge gap
→ goal-linked review task
→ generated practice
→ updated learning state
```

## What GitHub adds

GitHub gives the AI:

- a file tree;
- writeback;
- history;
- timestamps;
- traceable changes;
- a shared operating layer;
- a place for automation outputs.

This is why a normal AI project is not enough by itself.

## What memory adds

Memory or project instructions should store the user's stable preferences:

- GitHub is the main operating layer;
- local files are protected source material;
- one main AI workflow is preferred;
- English and Chinese stay in separate files;
- every change should be reported.

Changing learner state should remain inspectable in `learner-profile.md` and the target repository.

## What goals add

Goals prevent the repository from becoming a pile of files.

Every file should answer:

```text
Which goal does this serve?
```

If a file serves no current or future goal, it should be archived or lowered in priority.

## What knowledge gaps add

Knowledge gaps connect the learner profile, extracted models, and future practice.

They answer:

```text
What does the learner still fail to recognize, apply, explain, or transfer?
```

## What review adds

Review is not the final goal. Review is the floor of learning.

The system returns to old material so the user can learn something new from it.

## What automation adds

Automation should do two main jobs:

1. organize, critique, and revise the repository;
2. generate practice based on goals, knowledge gaps, history, and spaced repetition.

## Final shape

The simplest form is:

```text
one AI app
+ one target GitHub repository
+ one connector
+ memory or project rules
```

This is enough to run a personal GitLearnOS from a phone or computer.