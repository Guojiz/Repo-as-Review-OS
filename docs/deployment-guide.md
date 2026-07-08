# Deployment Guide

This is the file-address-first deployment guide for GitLearnOS.

The goal is lightweight deployment: exact files, exact state location, exact write boundary, and no fake capability claims.

## Non-negotiable principles

```text
one learner
→ one active learning runtime
→ one learning state layer
→ one handoff path
```

Do not turn GitLearnOS into a platform bundle where ChatGPT, Claude, OpenHanako, Codex, and Claude Code all write the same learning state at the same time.

## Repository roles

```text
Template repository
→ Guojiz/Repo-as-Review-OS
→ public method, docs, examples, skills, and rules

Learning state layer
→ the user's chosen target location
→ real goals, learner profile, sources, models, knowledge gaps, reviews, dashboard, handoff notes
```

Never write personal learning data into the template repository.

## State layer rule

Use GitHub as the default state layer, especially for ChatGPT and Claude.

```text
recommended default
→ GitHub target repository

local-first desktop alternative
→ local git repository
→ local git + Obsidian vault
```

For ChatGPT or Claude, a local path is not automatically writable. Use a local git folder or Obsidian vault only when the runtime actually has local file access, or when the AI gives exact patches for the user to apply manually.

For OpenHanako, local git or local git + Obsidian can be a real state layer because the desktop runtime can access local files when the user grants permission.

## First files to read

Read only these files first.

English route:

```text
README.md
START-HERE.md
QUICKSTART.md
docs/deployment-guide.md
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/skill-and-memory-runtime.md
docs/single-active-runtime-rule.md
AGENTS.md
```

Chinese route:

```text
README.zh-CN.md
START-HERE.zh-CN.md
QUICKSTART.zh-CN.md
docs/zh-CN/deployment-guide.md
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/skill-and-memory-runtime.md
docs/zh-CN/single-active-runtime-rule.md
AGENTS.zh-CN.md
```

Do not read all examples, all docs, all website files, or all skills during first deployment unless the user asks.

## Platform routes

### ChatGPT native platform

Read:

```text
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
```

Use ChatGPT for the native memory-first daily learning workflow. The default state layer should be a GitHub target repository. Scheduled prompts are handoff starters unless repository tools are live in that run.

### Claude native platform

Read:

```text
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
```

Claude means the native Claude platform, not Claude Code. Use Claude for project/artifact-first reading, writing, drafting, and long-context work. Artifacts are working surfaces, not the durable learning state.

### OpenHanako desktop runtime

Read:

```text
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
docs/deploy-openhanako-with-code-agents.md
```

OpenHanako / HanaAgent is the desktop enhanced runtime for local files, agent desks, memory, skills, scheduled tasks, channels, and subagents. It is optional, not required for basic GitLearnOS.

### Claude Code / Codex / Cursor

Read:

```text
docs/deploy-openhanako-with-code-agents.md
```

Use these only to deploy, inspect, debug, or customize OpenHanako. They should not become the maintained daily GitLearnOS tutoring layer unless the user deliberately wants a developer workflow.

## Minimal target state tree

Create or verify this in the chosen learning state layer:

```text
dashboard.md
learner-profile.md
GITLEARNOS.md
goals/main-goal.md
goals/goal-index.md
sources/source-index.md
models/model-index.md
knowledge-gaps/gap-index.md
reviews/review-index.md
reviews/due.md
templates/source-record-template.md
templates/model-card-template.md
templates/knowledge-gap-template.md
templates/review-card-template.md
agents/handoff-notes/latest.md
automations/README.md
archive/README.md
```

Create the folders needed for those files. Do not create extra subsystems during first deployment.

## First deployment content rule

Use `TBD` only for unknown fields. If the user already gave a learning goal, write it into `dashboard.md`, `learner-profile.md`, and `goals/main-goal.md`. If the user did not give a learning goal, ask for it before creating detailed content.

## Required local rule file

Create `GITLEARNOS.md` in the learning state layer:

```markdown
# GitLearnOS Local Rules

## Active runtime

TBD: ChatGPT / Claude / OpenHanako

## State layer

This folder or repository is the learning state layer.

## Rule

Use one active learning runtime at a time.

## Write boundary

Write learning state only inside this state layer.

Do not write personal learning data into the template repository.

## Source honesty

Mark sources as complete, excerpt-only, local-only, missing, or uncertain.

## Handoff

Before switching platforms, update agents/handoff-notes/latest.md.
```

## Native platform setup prompt

```text
You are helping me deploy GitLearnOS.

Template repository:
https://github.com/Guojiz/Repo-as-Review-OS

Use only one active runtime. Do not let ChatGPT, Claude, OpenHanako, Codex, or Claude Code update the same state layer in parallel.

Read only the deployment route first. Do not read the whole repository unless I ask.

My chosen active runtime is:
<ChatGPT / Claude / OpenHanako>

My learning state layer is:
<paste GitHub repository, local git folder, or Obsidian vault path>

If the state layer is local and you do not have local file access, do not claim to edit it. Give exact file contents or patches for me to apply manually.

Create or verify the minimal state tree. If I already gave a learning goal, use it. If not, ask for it before creating detailed learning content.

Report: active runtime, state layer, files read, files created, files changed, manual steps needed, and next action.
```

## OpenHanako source-grounded deployment facts

When using a code agent to deploy OpenHanako, verify against the actual `liliMozi/openhanako` source before changing anything.

Known source facts at the time this guide was written:

- `package.json` uses package name `hanako`, product name `HanaAgent`, main entry `desktop/bootstrap.cjs`, CLI bin `hana → cli/entry.ts`, and Node engine `>=24.12.0 <25`.
- `scripts/launch.js` is the cross-platform launcher and clears `ELECTRON_RUN_AS_NODE` before spawning Electron.
- `scripts/dev-env.js` sets development `HANA_HOME` to `~/.hanako-dev`.
- `server/index.ts` is a Hono HTTP + WebSocket server with routes for chat, sessions, models, agents, desk, skills, channels, filesystem, preferences, bridge, commands, resources, mobile workbench, media, and more.
- `core/agent.ts` models an Agent with identity, personality, memory, tools, and prompt-building logic.
- `lib/tools/subagent-tool.ts` supports delegated subagents with an optional `agent` target and optional `model` override; use the actual roster instead of inventing agent IDs.

## OpenHanako command order

Run in this order:

```bash
node -v
npm -v
npm install
npm run typecheck
npm test
npm run start:dev
```

`npm run start:vite` should not be treated as a standalone first-run command. Use it only when the renderer dev server is also running, for example with `npm run dev:renderer` in another terminal.

If desktop startup fails, inspect:

```text
scripts/launch.js
scripts/dev-env.js
Electron logs
HANA_HOME
ELECTRON_RUN_AS_NODE
```

If server startup fails, inspect:

```text
server/index.ts
npm run server output
```

Do not edit OpenHanako source during first deployment unless the build fails and the user explicitly approves a fix.

## Platform switching checklist

Before switching platforms:

```text
1. Update dashboard.md.
2. Update learner-profile.md.
3. Update knowledge-gaps/gap-index.md.
4. Update reviews/review-index.md.
5. Write agents/handoff-notes/latest.md.
6. Stop the old runtime.
7. Start the new runtime from latest.md.
```

Never let two platforms update the same state layer at the same time.

## Deployment success definition

Deployment is complete only when these are true:

```text
one active runtime chosen
one state layer chosen
minimal file tree created or exact manual patch provided
GITLEARNOS.md created or provided
learner-profile.md created or provided
dashboard.md created or provided
handoff note created or provided
first learning goal used or requested
no parallel runtime left active
```
