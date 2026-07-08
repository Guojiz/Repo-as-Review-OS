# Skill and Memory Runtime

Different AI environments load operating rules differently.

GitLearnOS actively supports two runtime families:

```text
ChatGPT native workflow
→ daily learning conversation, memory alignment, GitHub-assisted work, and light automation handoff

OpenHanako / HanaAgent desktop workflow
→ local files, multi-agent work, Skills, scheduled tasks, browser/computer actions, and deeper file automation
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

See `docs/deploy-openhanako-with-code-agents.md`.

Before choosing a runtime path, the AI should identify its current environment and adapt the setup plan. See `docs/runtime-self-adaptation.md` and `docs/platform-agent-configuration.md`.

## Recommended runtime tiers

```text
Actively supported daily platform: ChatGPT
→ recommended for daily learning conversation, reasoning, explanation, writing, memory alignment, source interpretation, GitHub-assisted work, and lightweight review generation

Actively supported desktop enhanced runtime: OpenHanako / HanaAgent
→ recommended when the learner wants a real desktop-side multi-agent system with local files, memory, Skills, scheduled tasks, browser/computer actions, and deeper automation

Deployment assistant: Claude Code / Codex / Cursor / repository-aware CLI agents
→ useful for deploying, debugging, or customizing OpenHanako
→ not the maintained daily tutoring layer

Lightweight single-context tier: Zhipu Qingyan, domestic single-context agents, and other chat-style AI tools
→ useful when the user can place a small set of rules, materials, and repository excerpts into one context window
```

Do not require a separate desktop agent by default. ChatGPT can complete many daily learning workflows through native platform features. OpenHanako is the recommended desktop enhancement when the user wants local file access, multi-agent coordination, Skills, and scheduled computer-side work.

For complete setup prompts and agent roles, see `docs/platform-agent-configuration.md`.

## Four runtime paths

```text
Path A: native ChatGPT workflow
→ use memory, project instructions, files, connectors, MCP, or GitHub integration when available
→ align native memory with learner-profile.md
→ keep GitHub as source of truth
→ use prompt-only automation as handoff unless live repository tools are available

Path B: OpenHanako / HanaAgent desktop workflow
→ configure GitLearnOS Maintainer, Source & Model Extractor, Practice & Review Coach, and optional Critic
→ use local desk files as protected source inbox
→ use GitHub as shared learning state
→ report every actual repository change

Path C: OpenHanako deployment with code agents
→ use Claude Code, Codex, Cursor, or a CLI agent to inspect and run OpenHanako source
→ use package scripts, not raw Electron commands
→ fix Node, npm, Electron, server, and packaging issues
→ after deployment, move GitLearnOS work into OpenHanako

Path D: single-context fallback
→ paste only the rules and excerpts needed for the current task
→ run one focused learning task
→ write valuable results back to GitHub manually or through a tool-enabled step
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

## Important distinction

Skill gives the AI behavior.

Memory gives the AI stable preferences.

Project space gives the AI fixed materials and conversation context.

Repository gives the AI current learning state.

Desktop runtime gives the AI local computer-side execution when available.

Code agents can deploy or debug the desktop runtime, but they are not the maintained daily learning layer.

Do not collapse these layers into one place.