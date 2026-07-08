# Deployment Guide

This is the AI-facing, file-address-first deployment guide for GitLearnOS.

The goal is lightweight deployment. Lightweight does not mean vague. It means the AI should know exactly what to read, what to create, what to update, and what to ignore.

Do not ask an AI to ingest the whole repository by default. Give it a route map.

## Core idea

```text
few files read
+ exact state layer
+ exact write targets
+ single active runtime
= lower token cost and less drift
```

## Non-negotiable principles

1. Keep the template repository and the learner's state layer separate.
2. Use one active learning runtime at a time.
3. Do not let ChatGPT, Claude, OpenHanako, Codex, Cursor, or Claude Code update the same state layer in parallel.
4. Code agents are deployment/debug helpers, not the daily learning tutor.
5. If the learner has already provided a learning goal, use it. If not, ask for it before creating detailed learning content.
6. Do not claim repository edits, local-file access, memory updates, scheduled work, or OpenHanako setup unless the runtime actually has that capability.
7. Report every file read, created, changed, or intentionally not touched.

## Repository roles

```text
Template repository
→ Guojiz/Repo-as-Review-OS
→ method, docs, examples, skills, public instructions

Learning state layer
→ the user's own target location
→ real goals, learner profile, sources, models, knowledge gaps, reviews, dashboard, handoff notes
```

Never write personal learning data into the template repository.

The learning state layer can be one of:

```text
GitHub target repository
local git repository
local git + Obsidian vault
```

GitHub is useful for cloud sync and cross-device work. Local git + Obsidian may be enough for a desktop OpenHanako setup.

## Canonical template repository

```text
Repository:
https://github.com/Guojiz/Repo-as-Review-OS

Repository full name:
Guojiz/Repo-as-Review-OS
```

## First read route

For an English deployment, read only these files first:

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

For a Chinese deployment, read only these files first:

```text
README.zh-CN.md
START-HERE.zh-CN.md
QUICKSTART.zh-CN.md
docs/zh-CN/deployment-guide.md
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/skill-and-memory-runtime.md
docs/zh-CN/single-runtime-rule.md
AGENTS.zh-CN.md
```

Do not read `examples/`, `website/`, all `docs/`, or all `skills/` during first deployment unless the user asks.

## Platform-specific route

### ChatGPT native platform

Read:

```text
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
```

Use ChatGPT as the active runtime only when the learner chooses ChatGPT for this deployment.

### Claude native platform

Read:

```text
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
```

Claude means the native Claude chat/project platform, not Claude Code.

### OpenHanako desktop runtime

Read:

```text
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
docs/deploy-openhanako-with-code-agents.md
```

Use OpenHanako when the learner wants a desktop agent workspace with local files, desk files, Skills, memory, selected scheduled tasks, channels, or multi-agent workflows.

### Claude Code / Codex / Cursor deployment helper

Read only deployment files:

```text
docs/deploy-openhanako-with-code-agents.md
```

Claude Code, Codex, Cursor, and similar tools should not become the daily GitLearnOS learning layer. They are only used to deploy, inspect, debug, or customize OpenHanako when the user explicitly wants that path.

## Minimal target state tree

Create this in the learner's chosen state layer.

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
agents/handoff-notes/index.md
agents/handoff-notes/latest.md
automations/README.md
automations/organizer-critic/index.md
automations/practice-generator/index.md
archive/README.md
```

Create these folders even if the first file is only an index:

```text
goals/
sources/
models/
knowledge-gaps/
reviews/
templates/
agents/
agents/handoff-notes/
automations/
automations/organizer-critic/
automations/practice-generator/
archive/
```

Do not create extra folders during first deployment.

## Required target files

### `dashboard.md`

Purpose: front page of the learner state.

Must contain:

```text
active goal
current subject
next action
due reviews
active knowledge gaps
last updated
handoff note link
```

### `learner-profile.md`

Purpose: inspectable learner memory.

Must contain:

```text
stable goal
preferred explanation style
current subjects
active knowledge gaps summary
recurring mistake patterns
resolved gaps
memory conflict notes
last updated
```

### `GITLEARNOS.md`

Purpose: local operating rule for the target state layer.

Must contain:

```text
single active runtime rule
state layer location
active platform
write boundaries
handoff rule
source honesty rule
```

### Index files

Create short index files for:

```text
goals/goal-index.md
sources/source-index.md
models/model-index.md
knowledge-gaps/gap-index.md
reviews/review-index.md
reviews/due.md
agents/handoff-notes/index.md
automations/README.md
archive/README.md
```

Each index should be short, link-based, and easy for an AI to scan.

## First deployment content templates

### `dashboard.md`

```markdown
# Dashboard

## Active goal

- Goal: TBD
- Stage: setup
- Last updated: YYYY-MM-DD

## Next action

- If the learner has already provided a learning goal, use it to fill `goals/main-goal.md`.
- If not, ask the learner for the first learning goal.

## Active knowledge gaps

- None recorded yet.

## Due reviews

- None yet.

## Handoff

- Latest handoff: agents/handoff-notes/latest.md
```

### `learner-profile.md`

```markdown
# Learner Profile

## Stable goal

TBD

## Preferred explanation style

TBD

## Current subjects

TBD

## Active knowledge gaps summary

None recorded yet.

## Recurring mistake patterns

None recorded yet.

## Resolved gaps

None recorded yet.

## Memory conflict notes

None.

## Last updated

YYYY-MM-DD
```

### `GITLEARNOS.md`

```markdown
# GitLearnOS Local Rules

## Active runtime

TBD: ChatGPT / Claude / OpenHanako

## State layer

This folder is the learning state layer.

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

### `agents/handoff-notes/latest.md`

```markdown
# Latest Handoff

## Active platform leaving

TBD

## New platform entering

TBD

## Current goal

TBD

## Last files updated

- None yet.

## Active gaps

- None yet.

## Next action

If the learner has already provided a learning goal, use it. If not, ask for the first learning goal.
```

## Minimal copy set from template repository

For a personal learning state layer, copy or recreate only these files:

```text
GITLEARNOS.md
learner-profile.md
dashboard.md
goals/main-goal.md
sources/source-index.md
models/model-index.md
knowledge-gaps/gap-index.md
reviews/review-index.md
reviews/due.md
agents/handoff-notes/latest.md
```

Do not copy every public demo, documentation file, website file, or issue template.

## Exact setup prompts

### ChatGPT setup prompt

```text
You are helping me deploy GitLearnOS in ChatGPT.

Template repository:
https://github.com/Guojiz/Repo-as-Review-OS

Read only these template files first:
- README.md
- START-HERE.md
- QUICKSTART.md
- docs/deployment-guide.md
- docs/native-ai-platform-deployment.md
- docs/platform-agent-configuration.md
- docs/single-active-runtime-rule.md

My state layer is:
<paste GitHub repo, local git folder, or Obsidian vault path>

Create or verify exactly these files:
- dashboard.md
- learner-profile.md
- GITLEARNOS.md
- goals/main-goal.md
- sources/source-index.md
- models/model-index.md
- knowledge-gaps/gap-index.md
- reviews/review-index.md
- reviews/due.md
- agents/handoff-notes/latest.md

Do not read the whole repository unless I ask.
Do not create extra folders unless needed.
Do not claim edits unless you can name changed files.
If I already gave a learning goal, use it. If not, ask me for my first learning goal before creating detailed learning content.
```

### Claude setup prompt

```text
You are helping me deploy GitLearnOS in Claude.

Template repository:
https://github.com/Guojiz/Repo-as-Review-OS

Read only these template files first:
- README.md
- START-HERE.md
- QUICKSTART.md
- docs/deployment-guide.md
- docs/native-ai-platform-deployment.md
- docs/platform-agent-configuration.md
- docs/single-active-runtime-rule.md

My state layer is:
<paste GitHub repo, local git folder, or Obsidian vault path>

Treat Claude Project context, files, memory, and artifacts as working surfaces. The state layer is the source of truth.

Create or verify exactly these files:
- dashboard.md
- learner-profile.md
- GITLEARNOS.md
- goals/main-goal.md
- sources/source-index.md
- models/model-index.md
- knowledge-gaps/gap-index.md
- reviews/review-index.md
- reviews/due.md
- agents/handoff-notes/latest.md

Use artifacts only for drafts, visual explanations, or temporary teaching material.
Persist durable learning state back to the state layer.
If I already gave a learning goal, use it. If not, ask me for my first learning goal before creating detailed learning content.
```

### OpenHanako setup prompt

```text
You are helping me deploy GitLearnOS in OpenHanako / HanaAgent.

Template repository:
https://github.com/Guojiz/Repo-as-Review-OS

Read only these template files first:
- README.md
- docs/platform-agent-configuration.md
- docs/single-active-runtime-rule.md
- docs/deployment-guide.md

My source folder is:
<paste local source folder path>

My state layer is:
<paste local git folder, Obsidian vault, or GitHub repository>

Create three agents only:
1. GitLearnOS Maintainer
2. Source & Model Extractor
3. Practice & Review Coach

Optional Critic only if I ask.

Enable only needed features:
- memory
- local file or desk access
- selected Skills

Do not enable broad file access.
Do not enable unnecessary scheduled tasks.
Do not let multiple platforms update the same state layer.
If I already gave a learning goal, use it. If not, ask me for my first learning goal before creating detailed learning content.
```

## OpenHanako source route for code agents

When using Claude Code, Codex, Cursor, or another code agent to deploy OpenHanako, inspect these OpenHanako source files first:

```text
Repository:
liliMozi/openhanako

README.md
package.json
scripts/launch.js
scripts/dev-env.js
server/index.ts
core/agent.ts
lib/tools/subagent-tool.ts
lib/tools/channel-tool.ts
scripts/build-server.mjs
```

Do not inspect the whole source tree first.

Do not modify source code during first deployment unless the build fails and the user approves a fix.

## OpenHanako command rule

Do not assume scripts exist. First read `package.json`, then run only scripts that are present.

Recommended order:

```bash
node -v
npm -v
npm install
npm run typecheck   # only if present
npm test            # only if present and useful
npm run start:dev   # only if present
```

If the repo uses a different start script, use the script declared in `package.json` and report the substitution.

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

If packaging is requested, use only a package script that exists in `package.json`, such as `dist`, `dist:win`, or `dist:linux`.

Do not package during first setup unless the user explicitly asks.

## Platform switching checklist

Before switching from ChatGPT to Claude, Claude to ChatGPT, native platform to OpenHanako, or OpenHanako to native platform:

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

## Token-saving rules

Use these rules during deployment:

```text
Read the route file first.
Read only platform-specific files next.
Create the skeleton before reading examples.
If the learner already gave a learning goal, use it; if not, ask for the first learning goal before detailed content.
Do not read examples unless the user asks for a demo.
Do not open all docs.
Do not copy website files.
Do not install all skills.
Do not create many agents.
```

## What to report after deployment

The AI must report:

```text
Active runtime:
State layer:
Files read:
Files created:
Files changed:
Files not touched:
Manual steps needed:
Next action:
```

If it cannot write files, it must say:

```text
I cannot write to the state layer in this runtime. Here are the exact files and contents for you to create manually.
```

## Deployment success definition

Deployment is complete only when these are true:

```text
one active runtime chosen
one state layer chosen
minimal file tree created
GITLEARNOS.md created
learner-profile.md created
dashboard.md created
handoff note created
first learning goal used or requested
no parallel runtime left active
```

If any item is missing, deployment is not complete.
