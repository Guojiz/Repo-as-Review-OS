---
name: repo-as-review-os
description: Use as the main router for GitLearnOS tasks. It decides whether to use setup, source handling, model extraction, review generation, or maintenance skills for a goal-driven AI learning repository built on GitHub.
---

# GitLearnOS Skill Router

## Purpose

Use this as the main entry skill for GitLearnOS.

GitLearnOS is a lightweight learning-trace operating system for AI-assisted study, built on GitHub.

It turns one repository into a writable learning timeline that an AI tool can read, edit, track, organize, generate practice from, and maintain over time.

## Skill suite

Use the most specific skill available:

```text
repo-as-review-os                  Main router for GitLearnOS
repo-as-review-os-setup            Create or migrate a learning repository
repo-as-review-os-source           Turn materials into honest source records
repo-as-review-os-model            Extract reusable learning models
repo-as-review-os-review           Generate review sets, drills, or mini tests
repo-as-review-os-maintenance      Audit, repair, and maintain the repository
```

## Routing rules

### Use setup when the user wants to create or migrate a repository

Use:

```text
skills/repo-as-review-os-setup/SKILL.md
```

For requests like:

```text
Set this up.
Create my GitLearnOS.
Copy the template into my repo.
Migrate my study repository.
```

### Use source when the user provides learning material

Use:

```text
skills/repo-as-review-os-source/SKILL.md
```

For requests like:

```text
Save this mistake.
Record this source.
This is only a partial note.
Turn this practice result into a source record.
```

### Use model when the user wants reusable understanding

Use:

```text
skills/repo-as-review-os-model/SKILL.md
```

For requests like:

```text
Turn this into a model.
Extract the method.
What is the reusable pattern?
Make this mistake useful next time.
```

### Use review when the user wants practice or repetition

Use:

```text
skills/repo-as-review-os-review/SKILL.md
```

For requests like:

```text
Generate a review set.
Make me a mini test.
What should I study today?
Give me practice from my knowledge gaps.
```

### Use maintenance when the repository needs repair or audit

Use:

```text
skills/repo-as-review-os-maintenance/SKILL.md
```

For requests like:

```text
Check this repo.
Clean up stale files.
Update the dashboard.
Find missing sources.
Prepare this for another agent.
```

## Core model

```text
goal
→ source
→ split
→ model
→ knowledge gap
→ practice set
→ spaced repetition
→ automation
→ new understanding
```

## Universal rules

1. Identify the user's goal.
2. Identify the repository and permission boundary.
3. Keep sources traceable.
4. Never treat a summary as a full source.
5. Never invent missing material.
6. Use private repositories for real learning data.
7. Write back only when the output has future value.
8. Update dashboard, learner profile, knowledge-gap records, or review fields when appropriate.
9. Report every file created or changed.

## If no subskill is available

Use this fallback task loop:

```text
task arrives
→ check goal
→ check source
→ check similar models
→ check knowledge gaps
→ answer or generate
→ write back if valuable
→ update index or dashboard
→ schedule review if needed
→ report changes and gaps
```

## If the environment does not support skills

Use memory, custom instructions, project instructions, or repository-level agent rules instead.

Suggested memory:

```text
Use GitHub as the main operating layer for my GitLearnOS. Treat local files as protected source material. Do not invent missing sources. Organize learning around goals, source records, reusable models, knowledge gaps, learner profile, spaced repetition, dashboards, and generated practice. Report every repository change. If a source is incomplete, label it honestly and add it to a queue instead of pretending it is complete.
```

## Output standard

```text
Changed files:
- path: what changed

Still missing:
- item or source needed

Next action:
- recommended next step
```