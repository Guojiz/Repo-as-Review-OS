# Skill and Memory Runtime

Different AI environments load operating rules differently.

Repo as Review OS supports both skill-based agents and memory-driven chat applications.

Before choosing a runtime path, the AI should identify its current environment and adapt the setup plan. See `docs/runtime-self-adaptation.md`.

## Two runtime paths

```text
Path A: skill-capable agent
→ install or copy the skill suite
→ start from the router skill
→ route to the specific subskill
→ connect GitHub repository
→ run the repository workflow

Path B: memory-driven AI app
→ connect GitHub repository
→ add core operating rules to memory or project instructions
→ run the repository workflow
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

For those tools, use memory, custom instructions, or project instructions.

Suggested memory:

```text
Use GitHub as the main operating layer for my personal learning OS. Treat local files as protected source material. Do not invent missing sources. Organize learning around goals, source records, reusable models, spaced repetition, dashboards, and generated practice. Report every repository change. If a source is incomplete, label it honestly and add it to a queue instead of pretending it is complete.
```

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

## Important distinction

Skill gives the AI behavior.

Memory gives the AI stable user preferences.

Repository gives the AI current learning state.

Do not collapse all three into one place.
