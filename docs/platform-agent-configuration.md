# Platform Agent Configuration

This guide explains how to configure GitLearnOS across three recommended runtime families:

```text
Daily native AI platform
→ ChatGPT or Claude

Desktop enhanced agent runtime
→ OpenHanako / HanaAgent

Code or CLI assistant
→ Codex, Claude Code, Cursor, or other repository-aware tools
```

The goal is not to force every platform into the same shape. The goal is to make each platform respect the same GitLearnOS learning loop:

```text
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review
```

## Runtime rule

Before setup, every AI tool must identify:

```text
runtime:
native memory:
project / workspace instructions:
GitHub read access:
GitHub write access:
local file access:
external memory tool:
desktop automation:
manual user steps:
```

Do not claim repository edits, local-file reading, scheduled work, or long-term memory unless that capability is actually available.

## Recommended platform map

```text
ChatGPT
→ recommended daily platform for reasoning, writing, explanation, memory alignment, GitHub-assisted work, and light automation handoff

Claude
→ recommended daily platform for reasoning, writing, long-context work, project-style organization, and GitHub/MCP-assisted work when available

OpenHanako / HanaAgent
→ recommended desktop enhanced runtime for local files, multi-agent work, skills, scheduled tasks, browser/desktop actions, and deeper file automation

Codex / Claude Code / Cursor / CLI agents
→ useful for coding, repository cleanup, scripts, bulk edits, and developer workflows
```

ChatGPT and Claude are not described here as desktop runtimes. Use their native platform features directly.

OpenHanako is the recommended desktop-side enhanced agent environment when the learner wants a computer-resident multi-agent system.

## ChatGPT native configuration

Use ChatGPT when the learner wants the smoothest daily study workflow.

### 1. Create or choose the target repository

Use one private GitHub repository for real learning data.

Suggested structure:

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

### 2. Add project instructions or a pinned setup prompt

Use this as the core instruction:

```text
You are helping me run GitLearnOS.

Use GitHub as the source of truth for my learning state. Local files are protected source material. ChatGPT memory is an active preference cache, not the canonical repository.

Before acting, identify your runtime, memory, file access, GitHub access, and permission boundary.

When studying, follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not invent missing sources. Do not claim repository edits unless you can report the changed files.
```

### 3. Use ChatGPT memory carefully

Suggested stable memory items:

```text
The user uses GitLearnOS for AI-assisted learning.
GitHub is the source of truth for learning state.
learner-profile.md stores the inspectable learner profile.
Local files are protected source material.
Practice should be generated from recent models and active knowledge gaps.
When ChatGPT memory conflicts with GitHub, trust GitHub first and suggest a memory update.
```

Do not store temporary tasks, raw private notes, stale gaps, or one-off practice results as permanent memory.

### 4. Connect GitHub if available

After connecting GitHub, ask ChatGPT to prove access:

```text
Check whether you can read my target repository and whether you can write to it. Report your exact access level. If you cannot write, do not pretend you can update files.
```

### 5. First run prompt

```text
Read this template repository: https://github.com/Guojiz/Repo-as-Review-OS

Help me set up GitLearnOS in this target repository:
<paste target repository>

First identify your runtime, memory capability, project context, GitHub read/write access, and manual steps I must complete.

Then create or verify dashboard.md, learner-profile.md, goals/main-goal.md, sources/, models/, knowledge-gaps/, reviews/, templates/, agents/, automations/, and archive/. Report every file created or changed.
```

### 6. Daily use prompt

```text
Use my GitLearnOS repository.

Read dashboard.md, learner-profile.md, recent models, active knowledge gaps, and recent reviews.

Tell me what I should study next, generate a small personalized practice set, and explain which source/model/gap each question targets.

If you update the repository, report every changed file.
```

### 7. Automation boundary

ChatGPT scheduled prompts should be treated as handoff starters unless the current run actually has repository tools.

Use this wording:

```text
This is a GitLearnOS handoff starter. If you do not have live GitHub access, do not claim repository work is done. Tell me what to inspect next and what command to send in a tool-enabled chat.
```

## Claude native configuration

Use Claude when the learner wants strong reasoning, writing, long-context work, and project-style organization.

### 1. Create a Claude project or equivalent workspace

Add only stable instructions and selected reference files.

Do not treat the Claude project as the learning repository.

Changing learning state belongs in GitHub:

```text
learner-profile.md
sources/
models/
knowledge-gaps/
reviews/
dashboard.md
```

### 2. Add Claude project instructions

```text
You are helping me run GitLearnOS.

Use my GitHub target repository as the source of truth. Use project files as reference material only.

Before acting, identify whether you have GitHub access, local file access, memory/project instruction support, MCP/tools, and write permission.

Follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not claim file edits unless you can name the changed files.
```

### 3. Connect GitHub or MCP if available

Ask Claude to confirm capability:

```text
Can you read my target GitLearnOS repository? Can you write to it? Can you use MCP or a connector? Can you access local files? Report the boundary before doing work.
```

### 4. Daily use prompt

```text
Read my GitLearnOS state: dashboard.md, learner-profile.md, active goals, recent models, knowledge-gaps/, and reviews/.

Generate today's next action and a small practice set from active knowledge gaps. Link each question to a source, model, or learner-profile entry. If you cannot read the repository, ask for the minimum excerpts instead.
```

### 5. Memory behavior

If Claude has native memory or persistent project context, store only stable preferences and durable patterns.

If it does not, keep the changing learner state in GitHub and ask for repository excerpts when needed.

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
- local desktop workspace and desk files.

## Why OpenHanako fits GitLearnOS

OpenHanako describes HanaAgent as an AI agent with memory, personality, proactive action, and multiple agents working together on the user's computer.

Its README lists file read/write, commands, terminal sessions, browser tools, search, screenshots, media preview, web inspection, Skills support, role cards, multi-agent collaboration, desk files, scheduled tasks, sandboxing, plugins, and multi-platform access.

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

Use one GitHub repository as the learning state layer:

```text
GitLearnOS-repo/
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

Local folders keep original materials. GitHub keeps the inspectable learning state.

### 3. Configure the Maintainer agent

System / personality instruction:

```text
You are the GitLearnOS Maintainer.

Your job is to keep the target GitHub repository coherent: dashboard.md, learner-profile.md, goals/, sources/, models/, knowledge-gaps/, reviews/, automations/, and archive/.

Before editing, identify file access, GitHub access, local access, memory status, and whether the current action is safe.

Never write personal learning data into the template repository. Only write into the user's target repository.

Report every changed file.
```

Suggested memory:

```text
GitLearnOS source of truth is the user's target GitHub repository.
Local files are protected source material.
learner-profile.md is the inspectable learner memory.
Knowledge gaps connect models to future practice.
```

### 4. Configure the Source & Model Extractor agent

Instruction:

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

Instruction:

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

Instruction:

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
Maintainer writes or approves final repository updates.
```

Keep GitHub as the shared state so agents do not drift into separate private memories.

### 8. Use the desk as the local source inbox

Put local files on the relevant agent desk:

```text
textbook excerpts
screenshots
PDF notes
paper snippets
raw mistakes
```

The agent should turn them into source records or model cards, not dump raw files into GitHub.

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
write only to the GitLearnOS target repository or controlled workspace
ask before deleting files
ask before uploading private material
ask before publishing real learning records
```

## Code / CLI assistant configuration

Use Codex, Claude Code, Cursor, or another CLI/code agent when the task is mostly repository maintenance, scripts, cleanup, or bulk editing.

Do not make them the default daily learning tutor unless the learner prefers a developer workflow.

Recommended prompt:

```text
You are maintaining a GitLearnOS repository.

Do not change the template repository unless explicitly asked. Work in the target repository.

Check dashboard.md, learner-profile.md, sources/, models/, knowledge-gaps/, reviews/, and automations/.

Make small reviewable changes. Report every changed file.
```

## Final choice rule

```text
Daily learning conversation
→ ChatGPT or Claude

Desktop multi-agent and local-file workflow
→ OpenHanako / HanaAgent

Repository scripts, coding, and bulk cleanup
→ Codex / Claude Code / Cursor / CLI agent

Long-term learning state
→ GitHub target repository

Original source material
→ local folders unless a small excerpt is needed
```
