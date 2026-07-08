# Skill and Memory Runtime

Different AI environments load operating rules differently.

Repo as Review OS supports skill-based agents, memory-driven chat applications, project-instruction workflows, and single-context AI tools.

Before choosing a runtime path, the AI should identify its current environment and adapt the setup plan. See `docs/runtime-self-adaptation.md`.

## Recommended runtime tiers

Do not write any single AI tool as the only entry point.

A safer runtime map is:

```text
Primary tier: Claude / ChatGPT
→ better for long tasks, complex reasoning, writing, coding, repository maintenance, and multi-step learning workflows

Lightweight tier: Zhipu Qingyan, domestic single-context agents, and other chat-style AI tools
→ useful when the user can place a small set of rules, materials, and repository excerpts into one context window

Enhanced tier: Codex, local agents, desktop automation tools
→ useful for bulk file operations, scripts, complex repository cleanup, and longer automation tasks
```

Do not require a separate desktop agent by default. ChatGPT or Claude on mobile can already complete many daily learning workflows. Desktop agents are enhancement options, not prerequisites.

## Two runtime paths

```text
Path A: skill-capable agent
→ install or copy the skill suite
→ start from the router skill
→ route to the specific subskill
→ connect GitHub repository
→ run the repository workflow

Path B: memory / project-instruction / single-context AI app
→ connect to or reference the GitHub repository
→ add core operating rules to memory, custom instructions, project instructions, or the current context
→ run a simplified repository workflow
```

## Skill path

Some AI agents support reusable skill packages.

Start with the router skill:

```text
skills/repo-as-review-os/SKILL.md
```

Then use the specific subskill when the task is clear:

```text
skills/repo-as-review-os-setup/SKILL.md
skills/repo-as-review-os-source/SKILL.md
skills/repo-as-review-os-model/SKILL.md
skills/repo-as-review-os-review/SKILL.md
skills/repo-as-review-os-maintenance/SKILL.md
```

## Skill suite roles

```text
repo-as-review-os                  Main router
repo-as-review-os-setup            Create or migrate a learning repository
repo-as-review-os-source           Turn materials into source records
repo-as-review-os-model            Extract reusable learning models
repo-as-review-os-review           Generate review sets, drills, or mini tests
repo-as-review-os-maintenance      Audit, repair, and maintain the repository
```

The skill suite gives the agent stable behavior.

It should not store changing personal learning data.

Changing data belongs in the user's repository:

```text
goals/
sources/
models/
reviews/
dashboard.md
automations/
```

## Memory path

Some AI apps may not support skill packages directly.

For those tools, use memory, custom instructions, project instructions, or the current context.

Suggested memory:

```text
Use GitHub as the main operating layer for my personal learning OS. Treat local files as protected source material. Do not invent missing sources. Organize learning around goals, source records, reusable models, spaced repetition, dashboards, and generated practice. Report every repository change. If a source is incomplete, label it honestly and add it to a queue instead of pretending it is complete.
```

## Single-context agent path

Some AI tools only have one context window, or they do not have stable skills, memory, or GitHub writeback.

This environment can still use the lightweight version of Repo as Review OS:

1. Copy only the repository rules needed for the current task.
2. Paste the relevant goal, source, model, or mistake excerpt.
3. Ask the AI to complete one task: organize, split, model, generate practice, or review.
4. Manually or tool-assisted write valuable results back to GitHub.

Do not ask a single-context agent to pretend it has long-term memory. It can execute the current task, but the long-term state still belongs in GitHub.

## New repository setup

When the user creates a new learning repository, the AI should copy or recreate the core Repo as Review OS structure into that repository.

Minimum private learning repository:

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

Minimum public template repository:

```text
README.md
OPERATING-MODEL.md
AGENT-RUNTIME.md
CONTRIBUTING.md
PUBLIC-ALPHA.md
docs/
templates/
examples/
skills/
```

## What should be copied

For a personal learning repository, copy the method and templates, not every public demo.

Recommended copy set:

```text
OPERATING-MODEL.md
AGENT-RUNTIME.md
docs/goal-model.md
docs/adaptive-rules.md
docs/spaced-repetition.md
docs/filesystem-design.md
docs/automation-model.md
templates/
skills/
```

If the target AI tool supports only one skill, copy only:

```text
skills/repo-as-review-os/
```

If it supports multiple skills, copy the whole `skills/` directory.

If the target AI tool only has one context window, copy only the minimum rules needed for the current task. Do not stuff the whole documentation set into one context.

## Important distinction

Skill gives the AI behavior.

Memory gives the AI stable preferences.

Project space gives the AI fixed materials and conversation context.

Repository gives the AI current learning state.

Do not collapse these layers into one place.