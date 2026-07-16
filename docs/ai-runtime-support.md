# AI Runtime Support

GitLearnOS supports any AI runtime that can execute the canonical learning contract honestly.

## Best experience

```text
tool-capable AI workspace
+ one private target repository
+ authorized source access when needed
+ GitLearnOS rules or Skills
```

ChatGPT Work is a strong direct path when its GitHub and source connections are available. A repository-aware coding agent is also a valid main runtime; it is not restricted to deploying another app.

## Minimum capability

The agent must be able to:

1. receive the active goal and relevant state;
2. elicit and observe a learner attempt;
3. follow source-integrity rules;
4. diagnose and adapt support;
5. report evidence and a next action;
6. write to the target or return exact pending writeback.

## Optional capabilities

Native memory, connected files, web research, code execution, visual generation, local-file access, automations, RAG, and subagents can improve the experience. None is mandatory for the basic loop.

## Unsupported behavior

A runtime is not suitable for autonomous writeback if it cannot identify its target, permissions, and changed files. It may still run the read-only fallback.

## Source of truth

The target repository stores changing learner state. Native memory caches stable preferences. The current chat performs current work. Do not collapse them into one hidden layer.
