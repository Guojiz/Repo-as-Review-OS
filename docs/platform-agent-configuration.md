# Platform Agent Configuration

This guide gives detailed GitLearnOS configuration for the main platform families this repository supports:

```text
Native AI platforms
→ ChatGPT
→ Claude

Desktop enhanced agent runtime
→ OpenHanako / HanaAgent

Code-agent deployment helpers
→ Claude Code / Codex / Cursor
```

Do not confuse Claude with Claude Code.

```text
Claude
→ native AI platform for learning conversation, projects, artifacts, long-context work, and writing

Claude Code
→ coding agent for deploying, inspecting, debugging, or customizing OpenHanako
```

For the native ChatGPT and Claude setup, see `docs/native-ai-platform-deployment.md`.

For OpenHanako deployment with code agents, see `docs/deploy-openhanako-with-code-agents.md`.

The supported platforms should respect the same GitLearnOS learning loop:

```text
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review
```

## Runtime rule

Before setup, every AI tool must identify:

```text
runtime:
native memory:
project / workspace instructions:
state layer:
repository or local git access:
local file access:
desktop automation:
manual user steps:
```

Do not claim repository edits, local-file reading, scheduled work, or long-term memory unless that capability is actually available.

## Recommended platform map

```text
ChatGPT
→ actively supported native daily learning platform
→ memory alignment, reasoning, explanation, writing, GitHub-assisted work, and light handoff automation

Claude
→ actively supported native daily learning platform
→ project-style organization, long-context reading, writing, artifacts, careful drafting, and repository-assisted work

OpenHanako / HanaAgent
→ actively supported desktop enhanced runtime
→ local files, multi-agent work, Skills, scheduled tasks, portable channels, browser/desktop actions, and deeper file automation

Claude Code / Codex / Cursor / CLI agents
→ supported only as OpenHanako deployment and source-code assistants
→ not maintained here as daily GitLearnOS tutoring platforms
```

ChatGPT and Claude are the two reference native platforms. Other chat-style AI tools should copy their pattern.

OpenHanako is the recommended desktop-side enhanced agent environment when the learner wants a computer-resident multi-agent system.

## Native platform setup

For ChatGPT and Claude, use:

```text
docs/native-ai-platform-deployment.md
```

The short version:

```text
ChatGPT
→ memory-first native workflow

Claude
→ project/artifact-first native workflow

GitHub / local git / Obsidian
→ durable learning state
```

Use only one active native platform at a time. Do not let ChatGPT and Claude both update the same learner-profile, knowledge gaps, reviews, or dashboard.

## ChatGPT native configuration

Use ChatGPT when the learner wants the smoothest daily web/mobile workflow and strong persistent personalization.

Minimum setup:

```text
state layer: GitHub, local git, or local git + Obsidian
active platform: ChatGPT
memory: stable preference cache
learner-profile.md: inspectable learner state
```

Core instruction:

```text
You are helping me run GitLearnOS in ChatGPT.

Use my chosen state layer as the source of truth for learning state. ChatGPT memory is an active preference cache, not the canonical repository.

Before acting, identify your runtime, memory, file access, repository access, and permission boundary.

Follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not invent missing sources. Do not claim file or repository edits unless you can name the changed files.
```

## Claude native configuration

Use Claude when the learner wants project-style organization, long-context reading, writing, artifacts, and careful revision.

Minimum setup:

```text
state layer: GitHub, local git, or local git + Obsidian
active platform: Claude
Claude Project: working surface
Artifacts: drafts, visual explanations, mini practice, or temporary teaching materials
learner-profile.md: inspectable learner state
```

Core instruction:

```text
You are helping me run GitLearnOS in Claude.

Use my chosen state layer as the source of truth for learning state. Claude project context, artifacts, and memory are working surfaces, not the canonical state.

Before acting, identify your runtime, memory/project capability, file access, repository access, and permission boundary.

Follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not invent missing sources. Do not claim file or repository edits unless you can name the changed files.

Use artifacts for drafts, visual explanations, tables, small apps, or temporary teaching materials. Persist important learning state back to learner-profile.md, sources/, models/, knowledge-gaps/, reviews/, or dashboard.md.
```

## OpenHanako / HanaAgent desktop configuration

Use OpenHanako when the learner wants a real desktop-side agent system.

OpenHanako is a better fit than generic desktop agents when GitLearnOS needs:

- local source material;
- file reading and writing;
- browser and computer-use actions;
- Skills;
- agent memory;
- scheduled tasks;
- multi-agent collaboration;
- local desktop workspace and desk files;
- portable channel access from messaging or social platforms.

## Why OpenHanako fits GitLearnOS

OpenHanako describes HanaAgent as an AI agent with memory, personality, proactive action, and multiple agents working together on the user's computer.

Its README lists file read/write, commands, terminal sessions, browser tools, search, screenshots, media preview, web inspection, Skills support, role cards, multi-agent collaboration, desk files, scheduled tasks, sandboxing, plugins, multi-platform bridge, mobile PWA, and LAN frontend support.

Its source also models each Agent as having its own identity, personality, memory, tools, and prompt-building logic.

## Recommended OpenHanako agent layout

Create three GitLearnOS agents:

```text
1. GitLearnOS Maintainer
   → owns repository structure, dashboard, learner-profile.md, indexes, and handoff notes

2. Source & Model Extractor
   → reads local excerpts or uploaded materials, creates source records, extracts reusable models, and records knowledge gaps

3. Practice & Review Coach
   → generates personalized practice from recent models, active knowledge gaps, review history, and spaced repetition
```

Optional fourth agent:

```text
4. Critic
   → audits vague notes, unsupported source claims, stale gaps, poor questions, and outdated learner-profile entries
```

Do not create many agents by default. Three agents are enough for most learners.

## OpenHanako state layer

On desktop, GitHub is useful but not mandatory.

Use one of:

```text
local git + Obsidian
local git repository
GitHub repository
```

Local git + Obsidian may be enough when the learner wants local-first control, fast editing, private notes, markdown navigation, and git history without cloud dependency.

Use GitHub when the learner needs cloud sync, cross-device handoff, public template sharing, or remote AI access.

## OpenHanako setup steps

### 1. Install and configure models

Follow OpenHanako's setup flow. Configure:

```text
conversation model
→ normal conversation and tutoring

small utility model
→ light tasks, routing, summaries, file checks

large tool model
→ memory compilation, deep analysis, source/model extraction, repository maintenance

vision model
→ screenshots, diagrams, handwritten notes, visual explanations when available
```

### 2. Create a GitLearnOS workspace

Use one local folder as the protected source layer:

```text
GitLearnOS-local/
├── textbooks/
├── screenshots/
├── papers/
├── raw-notes/
└── exports/
```

Use one learning state layer:

```text
GitLearnOS-state/
├── dashboard.md
├── learner-profile.md
├── goals/
├── sources/
├── models/
├── knowledge-gaps/
├── reviews/
├── automations/
└── archive/
```

Local folders keep original materials. The state layer keeps the inspectable learning state.

### 3. Configure the Maintainer agent

```text
You are the GitLearnOS Maintainer.

Your job is to keep the target learning state coherent: dashboard.md, learner-profile.md, goals/, sources/, models/, knowledge-gaps/, reviews/, automations/, and archive/.

Before editing, identify file access, state-layer access, local access, memory status, and whether the current action is safe.

Never write personal learning data into the template repository. Only write into the user's chosen state layer.

Report every changed file.
```

Suggested memory:

```text
GitLearnOS source of truth is the user's chosen state layer.
Local files are protected source material.
learner-profile.md is the inspectable learner memory.
Knowledge gaps connect models to future practice.
```

### 4. Configure the Source & Model Extractor agent

```text
You are the GitLearnOS Source & Model Extractor.

When given material, create an honest source record. Mark whether the source is complete, excerpt-only, local-only, missing, or uncertain.

Extract reusable models from problems, notes, papers, or mistakes.

Record knowledge gaps when the learner fails to recognize, apply, explain, or transfer a model.

Do not claim to have read a local file unless OpenHanako actually gave you access to it.
```

Output target:

```text
sources/
models/
knowledge-gaps/
```

### 5. Configure the Practice & Review Coach agent

```text
You are the GitLearnOS Practice & Review Coach.

Generate practice only from repository state: learner-profile.md, recent models, active knowledge gaps, source records, and review history.

Every question should link to a source, model, or knowledge-gap entry.

After practice, propose updates to learner-profile.md and next review dates.
```

Output target:

```text
reviews/
automations/practice-generator/
```

### 6. Configure the optional Critic agent

```text
You are the GitLearnOS Critic.

Audit the repository for vague notes, unsupported summaries, stale knowledge gaps, duplicated models, weak practice questions, and learner-profile entries that no longer match evidence.

Make small safe fixes only when clearly supported. Queue uncertain fixes instead of guessing.
```

Output target:

```text
automations/organizer-critic/
```

### 7. Use OpenHanako channels or delegation

Recommended workflow:

```text
Maintainer receives the user request.
Maintainer delegates source/model work to Source & Model Extractor.
Maintainer delegates practice generation to Practice & Review Coach.
Critic audits the result when needed.
Maintainer writes or approves final state-layer updates.
```

Keep the state layer shared so agents do not drift into separate private memories.

### 8. Use the desk as the local source inbox

Put local files on the relevant agent desk:

```text
textbook excerpts
screenshots
PDF notes
paper snippets
raw mistakes
```

The agent should turn them into source records or model cards, not dump raw files into the state layer.

### 9. Configure scheduled tasks

Use scheduled tasks for maintenance, not unchecked rewriting.

Recommended schedules:

```text
Daily or every 2 days:
→ check dashboard, learner-profile.md, active knowledge gaps, and due reviews

Weekly:
→ run Organizer + Critic + Revision

After each study session:
→ update learner-profile.md, record new gaps, schedule next review
```

Scheduled tasks must report what they actually read and changed.

### 10. Sandbox rule

Keep OpenHanako's file permissions narrow:

```text
read local source folder
write only to the GitLearnOS state layer or controlled workspace
ask before deleting files
ask before uploading private material
ask before publishing real learning records
```

## Deploy OpenHanako with Claude Code or Codex

Claude Code, Codex, Cursor, and similar tools can help deploy OpenHanako itself.

Use them for:

```text
source inspection
Node version checks
dependency installation
Electron startup debugging
server debugging
build or packaging troubleshooting
```

Do not use them as the maintained daily GitLearnOS tutoring layer.

See `docs/deploy-openhanako-with-code-agents.md` for the source-guided deployment checklist and safe prompt.

## Final choice rule

```text
Native daily learning conversation
→ ChatGPT or Claude

Desktop multi-agent and local-file workflow
→ OpenHanako / HanaAgent

Deploying or debugging OpenHanako source
→ Claude Code / Codex / Cursor / CLI code agent

Long-term learning state
→ GitHub target repository, local git, or local git + Obsidian

Original source material
→ local folders unless a small excerpt is needed
```
