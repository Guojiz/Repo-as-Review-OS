# Single Active Runtime Rule

GitLearnOS strongly recommends using one active learning runtime at a time.

Do not run ChatGPT, OpenHanako, Claude, Codex, Obsidian agents, and other tools as parallel learning authorities unless there is a deliberate handoff.

Multiple platforms at the same time create drift:

```text
native memory drift
+ private agent context drift
+ duplicate practice generation
+ conflicting learner-profile updates
+ different repository states
+ unclear source of truth
```

## Recommended rule

```text
one learner
→ one active learning runtime
→ one learning state layer
→ one handoff path
```

## Good setups

### Lightweight setup

```text
ChatGPT
→ daily learning runtime

GitHub target repository
→ source of truth for learning state

local files
→ protected original materials
```

### Desktop setup

```text
OpenHanako / HanaAgent
→ daily desktop learning runtime

local git + Obsidian or a GitHub repository
→ learning state layer

local files / desk files
→ protected original materials
```

### Deployment setup

```text
Claude Code / Codex / Cursor
→ deploy or debug OpenHanako only

OpenHanako
→ becomes the active learning runtime after deployment
```

## GitHub is optional on desktop

On a desktop OpenHanako setup, GitHub is useful but not mandatory.

A local git repository plus Obsidian may be enough when the learner wants local-first control, fast editing, private notes, markdown navigation, and git history without cloud dependency.

In that case, treat local git + Obsidian as the learning state layer.

Use GitHub only when the learner needs cloud sync, cross-device handoff, public template sharing, or remote AI access.

## Portable access channels

OpenHanako messaging or social integrations can improve portability.

Treat them as input and notification channels, not as separate learning state authorities.

```text
portable channel
→ quick input and notification

OpenHanako
→ active agent runtime

local git / Obsidian / GitHub
→ learning state layer
```

Important learning results should still be written back to the chosen state layer.

## Feature budget rule

OpenHanako has many features. Do not enable everything by default.

Enable only features needed for the current learning workflow.

```text
Usually useful:
- memory
- local file or desk access
- selected Skills
- one Maintainer agent
- one Source and Model Extractor
- one Practice and Review Coach

Enable only when needed:
- scheduled tasks
- portable channel integrations
- extra subagents
- Critic agent
- screenshots or vision

Avoid by default:
- broad file access
- too many agents
- uncontrolled scheduled rewrites
- parallel platform workflows
```

This prevents token waste, context drift, and state conflicts.

## Handoff rule

If switching platforms, do a deliberate handoff:

```text
1. Read current dashboard and learner-profile.
2. Read recent models, knowledge gaps, and reviews.
3. Write a handoff note.
4. Stop the old runtime.
5. Start the new runtime from the handoff note.
```

Never let two runtimes update the learning state at the same time.