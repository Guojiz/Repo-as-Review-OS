# Deployment Guide

Deployment attaches GitLearnOS to one learner-owned target repository and one main agent. It does not install a tutoring platform or multi-agent system.

## Tool-capable fast path

```text
1. identify the target and current goal/input
2. verify read/write/source/scheduler capability
3. inspect existing state
4. read START-HERE.md, AGENTS.md, and learning-policy.md
5. create only missing minimum state
6. organize the first real input or generate the first targeted questions
7. verify writeback and return a receipt
```

Minimum:

```text
AGENTS.md
learning-policy.md
dashboard.md
learner-profile.md
goals/main-goal.md
```

Create source, gap, model, handoff, review, or activity files only when real use requires them.

## Existing target

- inspect before writing;
- preserve unrelated files;
- map one active path first;
- reuse existing canonical state;
- ask before broad moves, overwrite, deletion, or policy change.

## Runtime selection

| Capability | Path |
|---|---|
| connected target read/write and source tools | direct Work path |
| local or cloud checkout | repository-agent path |
| context but no write | read-only pending-writeback path |
| pasted excerpts only | focused fallback |

ChatGPT Work is a standard direct path. Codex, Claude, Cursor, or another capable agent can also be the one main runtime. The current product does not need agent decomposition.

## Success test

Deployment succeeds when the learner can provide one natural-language event and the agent can:

- organize and link it;
- generate useful questions when requested or policy-triggered;
- write safe changes without path-by-path instruction;
- report actual automation and every changed file;
- honor preview, record-only, no-review, and undo boundaries.

Creating folders or running a forced AI session is not the success criterion.
