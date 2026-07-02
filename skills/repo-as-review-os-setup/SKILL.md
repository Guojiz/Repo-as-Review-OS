---
name: repo-as-review-os-setup
description: Use when creating or migrating a user's personal Repo as Review OS learning repository. This skill sets up the initial GitHub structure, goal file, dashboard, templates, runtime rules, and skill or memory fallback.
---

# Repo as Review OS Setup Skill

## Purpose

Use this skill to set up a new personal learning repository or migrate an existing repository into Repo as Review OS.

## When to use

Use when the user says things like:

- help me set this up;
- create my learning OS;
- migrate my study repository;
- build the folder structure;
- connect this repo to my AI agent;
- copy the Review OS template into my repo.

## Setup flow

1. Confirm the target GitHub repository.
2. Ask whether the repository will contain real learning data.
3. Recommend a private repository for real learning records.
4. Check the AI permission boundary.
5. Create or verify this minimal structure:

```text
dashboard.md
goals/main-goal.md
sources/
models/
reviews/
templates/
agents/
automations/
archive/
```

6. Copy or recreate core method files and templates.
7. Add skill runtime or memory fallback instructions.
8. Ask for the user's first learning goal before writing detailed personalized content.
9. Report every created or changed file.

## Recommended copy set

For a private personal learning repository, copy method and templates, not every public demo:

```text
OPERATING-MODEL.md
AGENT-RUNTIME.md
docs/goal-model.md
docs/adaptive-rules.md
docs/spaced-repetition.md
docs/filesystem-design.md
docs/automation-model.md
templates/
skills/repo-as-review-os/
```

## First goal prompt

Ask:

```text
What is the first learning goal you want this repository to support?
```

Examples:

```text
Improve SAT Reading and Writing in 6 weeks.
Review math mistakes every week.
Read three papers and remember the main ideas.
Organize daily English learning.
```

## Safety rules

Do not place private or copyrighted materials in a public repository.

For real study data, recommend a private repository.

Do not ask for broad GitHub account permissions when one-repository access is enough.

## Output standard

```text
Changed files:
- path: what changed

Still missing:
- item or user decision needed

Next action:
- recommended next setup step
```
