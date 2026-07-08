# Skill and Memory Runtime

Different AI environments load operating rules differently.

GitLearnOS actively supports three runtime families:

```text
ChatGPT native workflow
→ daily learning conversation, memory alignment, GitHub-assisted work, and light automation handoff

Claude native workflow
→ daily learning conversation, project-style organization, artifacts, long-context reading, writing, and careful revision

OpenHanako / HanaAgent desktop workflow
→ local files, multi-agent work, Skills, scheduled tasks, portable channels, browser/computer actions, and deeper file automation
```

Claude Code, Codex, Cursor, and other code or CLI agents are not maintained here as daily GitLearnOS tutoring runtimes.

They are useful as OpenHanako deployment assistants:

```text
Claude Code / Codex / Cursor / CLI code agent
→ inspect OpenHanako source
→ install dependencies
→ run and debug HanaAgent
→ troubleshoot Electron, server, Node, build, and packaging issues
→ then hand off daily learning work to OpenHanako
```

Do not confuse Claude with Claude Code.

```text
Claude
→ native AI platform

Claude Code
→ coding agent for deployment and source work
```

See `docs/deploy-openhanako-with-code-agents.md`.

Before choosing a runtime path, the AI should identify its current environment and adapt the setup plan. See `docs/runtime-self-adaptation.md`, `docs/native-ai-platform-deployment.md`, and `docs/platform-agent-configuration.md`.

## Recommended runtime tiers

```text
Actively supported native platform: ChatGPT
→ recommended for daily learning conversation, reasoning, explanation, writing, memory alignment, source interpretation, GitHub-assisted work, and lightweight review generation

Actively supported native platform: Claude
→ recommended for project-style learning, long-context reading, writing, artifacts, careful revision, and repository-assisted work

Actively supported desktop enhanced runtime: OpenHanako / HanaAgent
→ recommended when the learner wants a real desktop-side multi-agent system with local files, memory, Skills, scheduled tasks, portable channels, browser/computer actions, and deeper automation

Deployment assistant: Claude Code / Codex / Cursor / repository-aware CLI agents
→ useful for deploying, debugging, or customizing OpenHanako
→ not the maintained daily tutoring layer

Lightweight single-context tier: Zhipu Qingyan, domestic single-context agents, and other chat-style AI tools
→ useful when the user can place a small set of rules, materials, and state excerpts into one context window
```

Do not require a desktop agent by default. ChatGPT and Claude cover the main native-platform pattern. OpenHanako is the desktop enhancement when the user wants local file access, multi-agent coordination, Skills, portable channels, and scheduled computer-side work.

For complete setup prompts and agent roles, see `docs/native-ai-platform-deployment.md` and `docs/platform-agent-configuration.md`.

## Five runtime paths

```text
Path A: native ChatGPT workflow
→ use memory, project instructions, files, connectors, MCP, or GitHub integration when available
→ align native memory with learner-profile.md
→ keep chosen state layer as source of truth
→ use prompt-only automation as handoff unless live repository tools are available

Path B: native Claude workflow
→ use Projects, memory/project context, artifacts, files, connectors, MCP, or GitHub integration when available
→ keep artifacts as working surfaces
→ persist durable learning state back to learner-profile.md, sources/, models/, knowledge-gaps/, reviews/, or dashboard.md

Path C: OpenHanako / HanaAgent desktop workflow
→ configure GitLearnOS Maintainer, Source & Model Extractor, Practice & Review Coach, and optional Critic
→ use local desk files as protected source inbox
→ use GitHub, local git, or local git + Obsidian as shared learning state
→ report every actual state-layer change

Path D: OpenHanako deployment with code agents
→ use Claude Code, Codex, Cursor, or a CLI agent to inspect and run OpenHanako source
→ use package scripts, not raw Electron commands
→ fix Node, npm, Electron, server, and packaging issues
→ after deployment, move GitLearnOS work into OpenHanako

Path E: single-context fallback
→ paste only the rules and excerpts needed for the current task
→ run one focused learning task
→ write valuable results back to the state layer manually or through a tool-enabled step
```

## Native ChatGPT path

Use ChatGPT directly.

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
Use the chosen state layer as the source of truth for my GitLearnOS. Treat local files as protected source material. learner-profile.md is the inspectable learner memory. Organize learning around goals, source records, reusable models, knowledge gaps, spaced repetition, dashboards, and generated practice. When native memory conflicts with the state layer, trust the state layer first and suggest a memory update.
```

## Native Claude path

Use Claude directly.

The AI should configure:

```text
Claude Project or equivalent workspace
+ project instructions
+ selected files or connected repository when available
+ artifacts for drafts and teaching surfaces
+ learner-profile.md sync
+ source/model/gap/review workflow
```

Artifacts should not become the only learning state. If an artifact creates durable learning information, summarize it back into the chosen state layer.

Suggested project instruction:

```text
Use the chosen state layer as the source of truth for my GitLearnOS. Treat Claude Project context, artifacts, and memory as working surfaces. Persist important learning state back to learner-profile.md, sources/, models/, knowledge-gaps/, reviews/, or dashboard.md.
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

Use one state layer: GitHub, local git, or local git + Obsidian.

Keep the state layer shared. Do not let agents drift into separate private memories.

Use OpenHanako desk files as the local source inbox. Turn local materials into source records and model cards instead of dumping raw files into the state layer.

See `docs/platform-agent-configuration.md` for the full desktop setup.

## OpenHanako deployment path

Use Claude Code, Codex, Cursor, or another code agent only to prepare OpenHanako.

The deployment agent should read OpenHanako source, check Node version, run repository scripts, diagnose startup/build errors, and avoid touching user data without permission.

See `docs/deploy-openhanako-with-code-agents.md`.

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

The skill suite gives the agent stable behavior. It should not store changing personal learning data.

Changing data belongs in the user's chosen state layer:

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

Some AI tools only have one context window, or they do not have stable skills, memory, or writeback.

This environment can still use the lightweight version of GitLearnOS:

1. Copy only the rules needed for the current task.
2. Paste the relevant goal, learner profile, source, model, knowledge gap, or mistake excerpt.
3. Ask the AI to complete one task: organize, split, model, record gap, generate practice, or review.
4. Write valuable results back to the state layer manually or through a tool-enabled step.

Do not ask a single-context agent to pretend it has long-term memory. It can execute the current task, but the long-term state still belongs in the chosen state layer.

## New repository setup

Minimum private learning state:

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

## Important distinction

Skill gives the AI behavior.

Memory gives the AI stable preferences.

Project space gives the AI fixed materials and conversation context.

Repository, local git, or Obsidian gives the AI current learning state.

Desktop runtime gives the AI local computer-side execution when available.

Code agents can deploy or debug the desktop runtime, but they are not the maintained daily learning layer.

Do not collapse these layers into one place.