# Agent Runtime Guide

GitLearnOS does not provide its own model runtime. It attaches a lightweight tutoring protocol to the AI environment the learner already uses.

## Capability levels

### Level A — tool-capable workspace

The runtime can read the template, inspect authorized sources, and write to the target repository. A connected ChatGPT Work session is one example.

Use the direct path:

```text
verify access → inspect target → run learning task → write back → verify
```

### Level B — repository-aware workspace

The runtime works in a local or cloud checkout. Follow repository instructions, preserve unrelated changes, run the same learning-session protocol, and commit only in the authorized workflow.

### Level C — read-only or native chat

The runtime can teach and may read selected context, but cannot write the target. Produce a concise pending writeback block and never claim that GitHub changed.

### Level D — single-context fallback

The user supplies the active goal, relevant profile excerpt, and one task-relevant state file. Complete one learning loop; do not claim persistent memory or file access.

## Minimum read set

Read `START-HERE.md`, `AGENTS.md`, then only the active target files. Do not preload every platform guide, template, demo, or skill.

## Runtime responsibilities

The active runtime should:

- teach and elicit learner attempts;
- access authorized sources through available tools;
- diagnose observable knowledge gaps;
- adapt explanations and practice;
- verify with a fresh check;
- write durable evidence when possible;
- report capability limits honestly.

## State responsibilities

```text
target repository → canonical changing learning state
learner-profile.md → inspectable learner state
skills/rules → agent behavior
native memory → optional stable preference cache
connected/local originals → authorized source surfaces
current chat → temporary working context
```

## Permission rule

Ordinary target-state writes required by the user's learning request may proceed when authorized. Ask before deletion, large overwrite, visibility changes, private publication, secrets, or license changes.

## One-main-agent default

Use one main AI workflow. Subagents, local tools, RAG, visualizers, or automations are optional capabilities, not requirements. Shared canonical state must remain in the target repository.
