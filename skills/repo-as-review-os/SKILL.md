---
name: repo-as-review-os
description: Use when helping a user set up, migrate, maintain, or run a goal-driven AI learning operating system in a GitHub repository. This skill turns learning goals, sources, mistakes, notes, and review tasks into a structured repository workflow with dashboards, models, spaced repetition, and automation outputs.
---

# Repo as Review OS Skill

## Purpose

Use this skill to help a user run Repo as Review OS in their own GitHub repository.

Repo as Review OS is a goal-driven AI learning operating system built on GitHub.

It is not a normal notes folder, not a dump of files, and not a single AI chat. It is a writable learning timeline that an AI tool can read, edit, track, organize, generate practice from, and maintain over time.

## When to use this skill

Use this skill when the user asks to:

- create a personal learning OS;
- migrate study materials into a GitHub repository;
- organize notes, sources, mistakes, or review tasks;
- generate practice from their own weak points;
- create dashboards, goal files, source records, models, or review sets;
- maintain a learning repository with an AI agent;
- explain or apply Repo as Review OS.

## Core model

```text
goal
→ source
→ split
→ model
→ practice set
→ spaced repetition
→ automation
→ new understanding
```

## Default setup flow

When setting up a new user repository:

1. Confirm or create one target GitHub repository.
2. Copy the core Repo as Review OS files into that repository.
3. Create a minimal structure:

```text
review-os/
├── dashboard.md
├── goals/
├── inbox/
├── sources/
├── models/
├── reviews/
├── templates/
├── agents/
├── automations/
└── archive/
```

4. Create `goals/main-goal.md`.
5. Create `dashboard.md`.
6. Create source, model, and review templates.
7. Add AI runtime instructions.
8. Report every file created or changed.

## If the environment supports skills

Install or copy this skill package into the agent's skill directory if the agent supports file-based skills.

The skill package should include at minimum:

```text
skills/repo-as-review-os/SKILL.md
skills/repo-as-review-os/README.md
```

Then use this skill whenever the user works on their learning repository.

## If the environment does not support skills

Use memory, custom instructions, project instructions, or a repository-level agent file instead.

Add this memory instruction:

```text
Use GitHub as the main operating layer for my personal learning OS. Treat local files as protected source material. Do not invent missing sources. Organize learning around goals, source records, reusable models, spaced repetition, dashboards, and generated practice. Report every repository change. If a source is incomplete, label it honestly and add it to a queue instead of pretending it is complete.
```

## First-run checklist

Before editing a user's learning repository, check:

1. What is the user's main goal?
2. What repository should be used?
3. What permission level do you have?
4. Are there private or copyrighted materials that must stay local?
5. Is this a public template or a private real-learning repository?

## Task loop

For every learning task:

```text
task arrives
→ check goal
→ check source
→ check similar models
→ answer or generate
→ write back if valuable
→ update index or dashboard
→ schedule review if needed
→ report changes and gaps
```

## Source rules

Never treat a summary as a full source.

Never invent a missing question, passage, paper, teacher file, screenshot, or score report.

If the source is incomplete, create a source record and label what is missing.

Use these status labels when helpful:

```text
full-source
draft-full
index
summary-only
not-full-solution
local-only-source
needs-source
todo
model
generated-review
active-dashboard
```

## Privacy and safety

For public repositories, only use templates, methods, and cleaned or fictional examples.

Do not upload:

- private study records;
- teacher files;
- copyrighted textbook or test pages;
- private screenshots;
- real exam records;
- secrets, tokens, cookies, or account information.

For real learning data, recommend a private repository.

## Adaptive behavior

Principles are stable. Strategies are adjustable.

When time is short, create lightweight notes, mark missing parts, and backfill later.

When time is available, expand notes into full source records, models, dashboards, and review cycles.

Do not make the repository beautiful at the cost of learning.

## Output standard

When you finish a task, report:

```text
Changed files:
- path: what changed

Still missing:
- item or source needed

Next action:
- recommended next step
```
