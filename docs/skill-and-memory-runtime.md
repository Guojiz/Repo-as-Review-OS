# Skill and Memory Runtime

Different AI environments load operating rules differently.

GitLearnOS supports skill-based agents, memory-driven chat applications, project-instruction workflows, desktop multi-agent runtimes, and single-context AI tools.

Before choosing a runtime path, the AI should identify its current environment and adapt the setup plan. See `docs/runtime-self-adaptation.md` and `docs/platform-agent-configuration.md`.

## Recommended runtime tiers

Do not write any single AI tool as the only entry point.

A safer runtime map is:

```text
Daily native AI platform: ChatGPT / Claude
→ recommended for daily learning conversation, reasoning, explanation, writing, memory alignment, source interpretation, GitHub-assisted work, and lightweight review generation

Desktop enhanced agent runtime: OpenHanako / HanaAgent
→ recommended when the learner wants a real desktop-side multi-agent system with local files, memory, Skills, scheduled tasks, browser/computer actions, and deeper automation

Code / CLI assistant tier: Codex / Claude Code / Cursor / repository-aware CLI agents
→ useful for coding, scripts, repository cleanup, bulk edits, and developer workflows

Lightweight single-context tier: Zhipu Qingyan, domestic single-context agents, and other chat-style AI tools
→ useful when the user can place a small set of rules, materials, and repository excerpts into one context window
```

Do not require a separate desktop agent by default. ChatGPT or Claude can already complete many daily learning workflows through their native platform features. OpenHanako is the recommended desktop enhancement when the user wants local file access, multi-agent coordination, Skills, and scheduled computer-side work.

For complete setup prompts and agent roles, see `docs/platform-agent-configuration.md`.

## Two runtime paths

```text
Path A: native ChatGPT / Claude workflow
→ use memory, project instructions, files, connectors, MCP, or GitHub integration when available
→ align native memory with learner-profile.md
→ keep GitHub as source of truth
→ use prompt-only automation as handoff unless live repository tools are available

Path B: skill-capable or desktop agent workflow
→ install or copy the skill suite
→ start from the router skill
→ connect GitHub repository
→ optionally configure OpenHanako multi-agent roles
→ run the repository workflow

Path C: single-context fallback
→ paste only the rules and excerpts needed for the current task
→ run one focused learning task
→ write valuable results back to GitHub manually or through a tool-enabled step
```

## Native ChatGPT / Claude path

Use the native platform directly.

The AI should configure:

```text
stable instructions
+ native memory or project instructions when available
+ GitHub connector / MCP / app integration when available
+ learner-profile.md sync
+ source/model/gap/review workflow
```

Suggested memory:

```text
Use GitHub as the source of truth for my GitLearnOS. Treat local files as protected source material. learner-profile.md is the inspectable learner memory. Organize learning around goals, source records, reusable models, knowledge gaps, spaced repetition, dashboards, and generated practice. When native memory conflicts with GitHub, trust GitHub first and suggest a memory update.
```

## OpenHanako / HanaAgent desktop path

Use OpenHanako when the learner wants a desktop-side enhanced runtime.

Recommended GitLearnOS agents:

```text
GitLearnOS Maintainer
→ dashboard, learner-profile.md, indexes, repository structure, handoff notes

Source & Model Extractor
→ source records, model extraction, knowledge-gap records

Practice & Review Coach
→ personalized practice, review sets, next review dates

Optional Critic
→ audits vague notes, stale gaps, unsupported claims, weak questions, and learner-profile drift
```

Keep GitHub as the shared state. Do not let agents drift into separate private memories.

Use OpenHanako desk files as the local source inbox. Turn local materials into source records and model cards instead of dumping raw files into GitHub.

See `docs/platform-agent-configuration.md` for the full desktop setup.

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
repo-as-review-os                  Main router for GitLearnOS
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
learner-profile.md
sources/
models/
knowledge-gaps/
reviews/
dashboard.md
automations/
```

## Single-context agent path

Some AI tools only have one context window, or they do not have stable skills, memory, or GitHub writeback.

This environment can still use the lightweight version of GitLearnOS:

1. Copy only the repository rules needed for the current task.
2. Paste the relevant goal, learner profile, source, model, knowledge gap, or mistake excerpt.
3. Ask the AI to complete one task: organize, split, model, record gap, generate practice, or review.
4. Manually or tool-assisted write valuable results back to GitHub.

Do not ask a single-context agent to pretend it has long-term memory. It can execute the current task, but the long-term state still belongs in GitHub.

## New repository setup

When the user creates a new learning repository, the AI should copy or recreate the core GitLearnOS structure into that repository.

Minimum private learning repository:

```text
dashboard.md
learner-profile.md
goals/main-goal.md
sources/
models/
knowledge-gaps/
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
docs/platform-agent-configuration.md
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

Desktop runtime gives the AI local computer-side execution when available.

Do not collapse these layers into one place.