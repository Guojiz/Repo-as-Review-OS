# Repo as Review OS Skill

This folder contains a reusable skill package for AI agents that support file-based skills.

## What it does

The skill helps an AI agent set up, migrate, and maintain a Repo as Review OS learning repository.

It gives the agent a stable workflow for:

- reading the user's goal;
- creating a learning repository structure;
- tracking sources honestly;
- extracting reusable models;
- generating review sets;
- maintaining dashboards;
- applying spaced repetition;
- reporting repository changes.

## Files

```text
SKILL.md     Main skill instructions
README.md    This file
```

## Installation idea

If your AI agent supports skills, copy this folder into the agent's skill directory or import it using that agent's skill mechanism.

Expected package path:

```text
skills/repo-as-review-os/SKILL.md
```

Then ask the agent:

```text
Use the repo-as-review-os skill to help me set up a personal learning OS in my GitHub repository.
```

## If your AI tool does not support skills

Use the memory fallback instead.

Add this to memory, custom instructions, or project instructions:

```text
Use GitHub as the main operating layer for my personal learning OS. Treat local files as protected source material. Do not invent missing sources. Organize learning around goals, source records, reusable models, spaced repetition, dashboards, and generated practice. Report every repository change. If a source is incomplete, label it honestly and add it to a queue instead of pretending it is complete.
```

## First setup in a new repository

When a user creates a new learning repository, the AI should copy or recreate the core Repo as Review OS files inside it:

```text
OPERATING-MODEL.md
AGENT-RUNTIME.md
PUBLIC-ALPHA.md or private equivalent
CONTRIBUTING.md if public
templates/
docs/
examples/ only if useful
```

For a private personal learning repository, the AI should also create:

```text
dashboard.md
goals/main-goal.md
sources/
models/
reviews/
automations/
archive/
```

## Important rule

The skill is not the user's memory.

The skill provides stable operating behavior. The user's changing goals, weak points, sources, and review history should live in the user's learning repository.
