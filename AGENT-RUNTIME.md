# Agent Runtime Guide

GitLearnOS does not provide a model runtime. It attaches automatic organization, targeted question generation, and learner-controlled writeback to one main AI environment chosen by the learner.

## Capability levels

### Level A — tool-capable workspace

The runtime reads the template and authorized sources and writes the target. A connected ChatGPT Work workspace is a standard example.

```text
verify access
→ read policy and active state
→ organize or generate questions
→ write back automatically
→ verify and return a receipt
```

### Level B — repository workspace

The runtime works in a local or cloud checkout. Follow repository rules, preserve unrelated changes, and execute the same organization, question, and writeback contract.

### Level C — read-only chat

The runtime can process input and generate questions but cannot write. Return exact pending writeback and do not claim the target changed.

### Level D — single-context fallback

The learner supplies the active goal, policy summary, and one relevant state file. Complete one focused operation without claiming persistent memory or file access.

## Minimum reading

Read `START-HERE.md`, `AGENTS.md`, target `learning-policy.md`, and dashboard, then only files required by the current input.

## Runtime responsibilities

- accept input from teachers, class, paper, platforms, and AI;
- organize, connect, and deduplicate automatically;
- generate targeted questions from goals and evidence;
- tutor and score only when useful;
- write within safety boundaries and report;
- distinguish immediate, on-handoff, and background automation;
- report capability limits honestly.

## State responsibilities

```text
target repository → canonical durable state and learner policy
skills/rules → agent behavior
native memory → optional stable-preference cache
connected/local originals → authorized sources
current workspace → temporary execution
```

## One main agent

One capable main agent is the current standard. Do not split organization, question generation, tutoring, and maintenance into separate agents. Other tools remain capabilities of the main agent, not independent state owners.

## Permission

Under `safe-auto`, ordinary low-risk reversible writes may proceed. Ask before deletion, broad overwrite, policy changes, publication, sensitive identity, secrets, or license changes.
