# Native AI Platform Deployment

This guide covers the two native AI platforms that GitLearnOS should treat as reference implementations:

```text
ChatGPT
→ native memory-first learning platform

Claude
→ native project/artifact-first learning platform
```

Other chat platforms can copy this pattern.

Do not confuse Claude with Claude Code. Claude is the native chat platform at claude.ai or the Claude app. Claude Code is a coding agent and belongs in the OpenHanako deployment path, not in the daily learning runtime.

## Core rule

Use only one active learning platform at a time.

```text
one learner
→ one active native AI platform
→ one learning state layer
→ one handoff path
```

If the learner uses ChatGPT today, ChatGPT is the active runtime.

If the learner uses Claude today, Claude is the active runtime.

Do not let both update the learner profile, knowledge gaps, reviews, or dashboard at the same time.

## Shared GitLearnOS loop

Both ChatGPT and Claude should run the same loop:

```text
source
→ model
→ knowledge gap
→ personalized practice
→ review result
→ learner-profile.md
→ next review
```

The platform may remember preferences, but the durable learning state should remain inspectable in the chosen state layer.

The state layer can be:

```text
GitHub repository
local git repository
local git + Obsidian vault
```

GitHub is recommended when the learner needs cloud sync, cross-device handoff, public templates, or remote AI access.

Local git + Obsidian is enough when the learner works mainly on one computer and wants a local-first setup.

## ChatGPT deployment

Use ChatGPT when the learner wants the smoothest mobile/web daily learning workflow and strong persistent personalization.

### 1. Choose state layer

Pick one:

```text
GitHub target repository
local git repository
local git + Obsidian vault
```

Minimum structure:

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

### 2. Create a project or pinned workflow

Use this instruction:

```text
You are helping me run GitLearnOS in ChatGPT.

Use my chosen state layer as the source of truth for learning state. ChatGPT memory is an active preference cache, not the canonical repository.

Before acting, identify your runtime, memory, file access, repository access, and permission boundary.

Follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not invent missing sources. Do not claim file or repository edits unless you can name the changed files.
```

### 3. Configure memory

Store only stable preferences:

```text
The user uses GitLearnOS for AI-assisted learning.
The chosen state layer is the source of truth.
learner-profile.md stores the inspectable learner profile.
Practice should be generated from recent models and active knowledge gaps.
When memory conflicts with the state layer, trust the state layer first and suggest a memory update.
```

Do not store temporary tasks, raw private notes, stale gaps, or one-off practice results as permanent memory.

### 4. Daily prompt

```text
Use my GitLearnOS state.

Read dashboard.md, learner-profile.md, recent models, active knowledge gaps, and recent reviews.

Tell me what I should study next. Generate a small personalized practice set. Explain which source, model, or gap each question targets.

If you update files, report every changed file.
```

### 5. Scheduled prompt boundary

If ChatGPT scheduled prompts do not have live repository tools, they are handoff starters only.

```text
This is a GitLearnOS handoff starter. If you do not have live repository access, do not claim repository work is done. Tell me what to inspect next and what command to run in a tool-enabled chat.
```

## Claude deployment

Use Claude when the learner wants a strong native platform for long-context reading, writing, artifacts, project-style organization, and careful drafting.

### 1. Choose state layer

Pick one:

```text
GitHub target repository
local git repository
local git + Obsidian vault
```

The state layer remains the source of truth.

Claude projects, project files, artifacts, and memory are working surfaces. They are not the canonical learning state unless the user deliberately makes them the only state layer for a short experiment.

### 2. Create a Claude project or equivalent workspace

Use one Claude project per major learning workflow.

Add only stable reference files and instructions.

Do not upload the entire universe into the project. Keep the project light enough for Claude to follow.

### 3. Add Claude project instructions

```text
You are helping me run GitLearnOS in Claude.

Use my chosen state layer as the source of truth for learning state. Claude project context, artifacts, and memory are working surfaces, not the canonical state.

Before acting, identify your runtime, memory/project capability, file access, repository access, and permission boundary.

Follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not invent missing sources. Do not claim file or repository edits unless you can name the changed files.

Use artifacts for drafts, visual explanations, tables, small apps, or temporary teaching materials. Persist important learning state back to learner-profile.md, sources/, models/, knowledge-gaps/, reviews/, or dashboard.md.
```

### 4. Claude memory and project context rule

Use Claude memory or project context for stable preferences and durable working assumptions.

Good candidates:

```text
preferred explanation style
current learning goal
state layer location
repository structure
recurring learning pattern
formatting conventions
```

Do not use memory as the only record of:

```text
active knowledge gaps
one-off practice answers
temporary deadlines
raw private notes
unverified source claims
```

### 5. Claude daily prompt

```text
Use my GitLearnOS state.

Read dashboard.md, learner-profile.md, recent models, active knowledge gaps, and recent reviews from the provided files or connected repository.

Give me the next action, then generate a compact practice set. For every question, say which source, model, or gap it targets.

Use an artifact only if it helps me review, visualize, or edit the result. Persist important state back to the chosen state layer.
```

### 6. Claude artifact rule

Artifacts are useful for:

```text
lesson drafts
visual explanations
interactive mini practice
comparison cards
small dashboards
writing revisions
```

Artifacts should not become the only place where learning state lives.

If an artifact creates durable learning information, write the summary back to the state layer.

## Switching between ChatGPT and Claude

Switch only with a deliberate handoff:

```text
1. Read dashboard.md and learner-profile.md.
2. Read recent models, knowledge gaps, and reviews.
3. Write a handoff note.
4. Stop the old platform.
5. Start the new platform from the handoff note.
```

Do not keep both platforms active on the same learning state.

## Pattern for other platforms

Other native AI platforms can copy the ChatGPT / Claude pattern:

```text
native memory or project context
→ stable preference cache

files, artifacts, or project uploads
→ working surface

GitHub / local git / Obsidian
→ durable learning state

handoff note
→ safe platform switch
```

If a platform cannot clearly report what it read, remembered, or changed, use it only as a single-context helper.

## Relationship to OpenHanako

OpenHanako is not a replacement for ChatGPT or Claude as native web/mobile AI platforms.

It is the desktop enhanced path for local files, desk files, Skills, scheduled tasks, bridge channels, and multi-agent workflows.

Use OpenHanako when the learner wants the computer itself to become the agent workspace.

Use Claude Code, Codex, or Cursor only to deploy or debug OpenHanako, then hand daily learning work back to OpenHanako.