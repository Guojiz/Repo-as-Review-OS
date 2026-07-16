# AI Runtime Support

GitLearnOS supports any one main AI runtime that can execute the learner-owned control contract honestly.

## Best experience

```text
tool-capable workspace
+ one private target repository
+ authorized sources when needed
+ GitLearnOS rules or skills
```

ChatGPT Work is a standard direct path when repository and source connections are available. A repository-aware coding agent is also valid.

## Minimum capability

The agent can:

1. receive a goal or learning event;
2. read minimum relevant state;
3. organize and connect input;
4. generate targeted, scoreable questions;
5. follow source and user-policy rules;
6. write the target or return exact pending writeback;
7. report actual automation and changed files.

Live tutoring is optional.

## Optional capability

Native memory, connected files, web research, code execution, visual generation, local-file access, and a real scheduler may improve execution. The current standard does not require subagents, a multi-agent framework, RAG, or a database.

## Unsupported behavior

A runtime is unsuitable for autonomous writeback when it cannot identify target, permissions, policy, or changed files. It may still use the read-only path.

## Source of truth

The target stores changing learner state and policy. Native memory caches stable preferences. The current workspace performs temporary work. Do not collapse them into hidden runtime memory.
