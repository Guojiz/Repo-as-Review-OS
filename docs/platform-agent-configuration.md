# Platform Agent Configuration

This guide gives AI-facing configuration rules for the platform families GitLearnOS can use.

It must not change the product principle:

```text
GitLearnOS core
→ one active learning runtime
→ one learning state layer
→ source records, models, gaps, reviews, dashboard
```

Platform guides are adapters, not new product identities.

## Platform roles

```text
ChatGPT
→ native daily learning runtime
→ best default with a GitHub target repository

Claude
→ native daily learning runtime
→ best for project-style reading, writing, artifacts, and long-context work

OpenHanako / HanaAgent
→ optional desktop enhanced runtime
→ useful for local files, desks, Skills, channels, scheduled tasks, and limited multi-agent work

Claude Code / Codex / Cursor / CLI agents
→ deployment and source-code assistants for OpenHanako
→ not the maintained daily learning layer
```

Do not confuse Claude with Claude Code.

```text
Claude
→ native AI platform for learning conversation, projects, artifacts, long-context work, and writing

Claude Code
→ coding agent for deploying, inspecting, debugging, or customizing OpenHanako
```

## Runtime self-check

Before setup, every AI tool must identify:

```text
runtime:
state layer:
read access:
write access:
local file access:
repository access:
memory / project instructions:
desktop automation:
manual user steps:
```

Do not claim repository edits, local-file reading, scheduled work, or long-term memory unless that capability is actually available.

## State layer boundary

For ChatGPT and Claude, prefer GitHub as the state layer.

```text
native platform default
→ GitHub target repository

native platform local path
→ only if the runtime has actual local file access
→ otherwise provide manual file contents or patches

OpenHanako desktop path
→ local git or local git + Obsidian can be real state layers when file access is granted
```

## Shared GitLearnOS loop

All supported platforms should respect the same loop:

```text
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review
```

The loop is more important than the platform brand.

## ChatGPT native configuration

Use ChatGPT when the learner wants smooth daily web/mobile learning and persistent personalization.

Minimum configuration:

```text
active runtime: ChatGPT
state layer: GitHub target repository unless proven otherwise
memory: stable preference cache
learner-profile.md: inspectable learner state
```

Core instruction:

```text
You are helping me run GitLearnOS in ChatGPT.

Use my chosen state layer as the source of truth. Prefer a GitHub target repository. ChatGPT memory is an active preference cache, not the canonical learning repository.

Before acting, identify your runtime, memory, file access, repository access, and permission boundary.

Follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not invent missing sources. Do not claim file or repository edits unless you can name the changed files.
```

## Claude native configuration

Use Claude when the learner wants project-style organization, long-context reading, writing, artifacts, and careful revision.

Minimum configuration:

```text
active runtime: Claude
state layer: GitHub target repository unless proven otherwise
Claude Project: working surface
Artifacts: drafts, visual explanations, mini practice, or temporary teaching materials
learner-profile.md: inspectable learner state
```

Core instruction:

```text
You are helping me run GitLearnOS in Claude.

Use my chosen state layer as the source of truth. Prefer a GitHub target repository unless I explicitly choose a local-first workflow and you have actual local file access. Claude project context, artifacts, and memory are working surfaces, not the canonical state.

Before acting, identify your runtime, memory/project capability, file access, repository access, and permission boundary.

Follow this loop:
source → model → knowledge gap → personalized practice → review result → learner-profile.md → next review.

Do not invent missing sources. Do not claim file or repository edits unless you can name the changed files.

Use artifacts for drafts, visual explanations, tables, small apps, or temporary teaching materials. Persist important learning state back to learner-profile.md, sources/, models/, knowledge-gaps/, reviews/, or dashboard.md.
```

## OpenHanako / HanaAgent desktop configuration

Use OpenHanako only when the learner wants a real desktop-side runtime.

Good reasons to use it:

- local source material;
- local file reading and writing;
- agent desks;
- Skills;
- scheduled tasks;
- bridge channels;
- browser and computer-use actions;
- limited multi-agent delegation inside one active desktop runtime.

Do not present OpenHanako as required for basic GitLearnOS. Do not let it run in parallel with ChatGPT or Claude on the same state layer unless there is a deliberate handoff.

## Source-grounded OpenHanako facts

The OpenHanako / HanaAgent guidance here is based on the actual `liliMozi/openhanako` source, not guessed from the name.

Current verified facts:

```text
package.json
→ name: hanako
→ productName: HanaAgent
→ main: desktop/bootstrap.cjs
→ bin: hana → cli/entry.ts
→ node: >=24.12.0 <25

scripts/launch.js
→ cross-platform launcher
→ clears ELECTRON_RUN_AS_NODE before spawning Electron

scripts/dev-env.js
→ development HANA_HOME = ~/.hanako-dev

server/index.ts
→ Hono HTTP + WebSocket server
→ routes include chat, sessions, models, agents, desk, skills, channels, filesystem, preferences, bridge, commands, resources, mobile workbench, media

core/agent.ts
→ Agent has identity, personality, memory, tools, and prompt-building logic

lib/tools/subagent-tool.ts
→ supports delegated subagents
→ optional agent target
→ optional model override
```

If those source facts change upstream, update this guide before changing GitLearnOS deployment instructions.

## Recommended OpenHanako agent layout

Inside OpenHanako, multiple agents are allowed only as roles within one active desktop runtime.

Default layout:

```text
1. GitLearnOS Maintainer
   → owns dashboard, learner-profile.md, indexes, handoff notes, and write boundary

2. Source & Model Extractor
   → turns local excerpts or uploaded materials into source records, models, and knowledge gaps

3. Practice & Review Coach
   → generates practice from recent models, active gaps, review history, and spaced repetition
```

Optional only when needed:

```text
4. Critic
   → audits vague notes, unsupported source claims, stale gaps, poor questions, and outdated learner-profile entries
```

The Maintainer is the final writer. Other agents propose or prepare work. This prevents multi-agent drift.

## OpenHanako state layer

On desktop, GitHub is useful but not mandatory.

Use one of:

```text
local git + Obsidian
local git repository
GitHub repository
```

Local folders keep original materials. The state layer keeps inspectable learning state.

Keep file permissions narrow:

```text
read local source folder
write only to the GitLearnOS state layer or controlled workspace
ask before deleting files
ask before uploading private material
ask before publishing real learning records
```

## Code-agent deployment helpers

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

## Final choice rule

```text
Native daily learning conversation
→ ChatGPT or Claude

Desktop local-file / multi-agent workflow
→ OpenHanako / HanaAgent

Deploying or debugging OpenHanako source
→ Claude Code / Codex / Cursor / CLI code agent

Long-term learning state
→ GitHub target repository by default
→ local git / Obsidian only when the active runtime can actually access it

Original source material
→ local folders unless a small excerpt is needed
```
