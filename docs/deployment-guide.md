# Deployment Guide

GitLearnOS deployment means attaching the toolkit to one learner-owned target repository. It does not mean installing a new tutoring platform.

## Fast path: tool-capable workspace

Use when the current AI can read the template and write the target—for example, an authorized ChatGPT Work session.

```text
1. identify target repository and active goal
2. verify read/write capability through available tools
3. inspect existing target files
4. read START-HERE.md and AGENTS.md
5. create only missing minimum state
6. run the first learning session
7. verify and report writeback
```

Minimum initial state:

```text
AGENTS.md
dashboard.md
learner-profile.md
goals/main-goal.md
```

Add the first source, model, gap, review, or session file when real learning creates it. Do not copy every template doc, demo, platform guide, or skill into the target by default.

## Existing target

- inspect before writing;
- preserve unrelated files;
- map one active learning path first;
- ask before large moves, overwrites, or deletion;
- do not create a parallel state system when existing files already serve the role.

## Read-only fallback

Provide exact Markdown writeback blocks and label them pending. The learner can apply them manually or return in a tool-capable session.

## Runtime selection

Choose by capability:

| Capability | Path |
|---|---|
| connected target read/write and source tools | direct Work path |
| local or cloud repository checkout | repository-agent path |
| teaching/context but no write access | read-only handoff path |
| only pasted excerpts | single-task fallback |

ChatGPT, Codex, Claude, Cursor, or another agent can be the main runtime if it has the required capabilities and the user chooses it. OpenHanako is an optional desktop adapter, not the default dependency.

## Success test

Deployment is complete only when the agent can identify the active goal, run an attempt-first learning session, record observable evidence, update the correct state file, and report one next action.

Creating folders alone is not successful deployment.
