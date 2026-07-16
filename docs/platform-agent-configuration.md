# Agent Runtime Configuration

Configure GitLearnOS by capability, not by brand hierarchy.

## Required contract

Every active agent should follow:

```text
one target repository
→ one canonical state per fact
→ attempt before mastery claim
→ evidence-linked writeback
→ one explicit next action
```

## Capability matrix

| Runtime capability | Configuration |
|---|---|
| repository and connected-source tools | direct execution; verify then write |
| repository checkout and file tools | follow local instructions and preserve worktree |
| native memory but no write access | teach actively; return pending writeback |
| no stable memory or files | one focused task from pasted state |

## ChatGPT Work example

```text
state: private GitHub target repository
behavior: GitLearnOS router or AGENTS.md
sources: connected files/apps only when authorized
memory: stable preference cache only
writeback: canonical target files
```

The agent should use available tools directly and should not ask the learner to reproduce operations it can safely perform.

## Repository-agent example

Codex, Claude Code, Cursor, or a similar agent can run GitLearnOS directly when it is the chosen active runtime. It should read repository instructions, inspect existing changes, and use the same learning evidence standard.

## Optional desktop or multi-agent adapters

OpenHanako, local agents, subagents, RAG systems, and schedulers may extend the toolkit. They are optional. Use one final writer and keep canonical learner state shared; do not let private agent memories diverge into competing sources of truth.

## Memory instruction

```text
Use the target repository as canonical GitLearnOS state. Use native memory only for stable preferences and durable patterns. When memory and repository evidence conflict, inspect timestamps and update the stale layer explicitly.
```

## Honest reporting

Always report actual read/write/source access. A drafted prompt is not an automation; a proposed patch is not a repository update; a generated review is not learner evidence until attempted.
