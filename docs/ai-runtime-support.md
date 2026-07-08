# AI Runtime Support

This page is a supplementary guide.

For the current main runtime path, read:

- [Runtime Self-Adaptation](runtime-self-adaptation.md)
- [Automation Runtime Matrix](automation-runtime-matrix.md)
- [Local Runtime Note](local-runtime-note.md)
- [Skill and Memory Runtime](skill-and-memory-runtime.md)
- [Single Active Runtime Rule](single-active-runtime-rule.md)

## Core idea

GitLearnOS is not tied to one AI product, but it does require a clear runtime boundary.

A tool is useful only if it can honestly say what it can read, what it can write, and where the durable learning state lives.

## Required capabilities

A good daily runtime should provide:

1. repository or state-layer access;
2. file creation and editing, or exact manual patches when it cannot edit;
3. project rules or stable memory;
4. permission boundaries;
5. honest source handling;
6. change reporting.

## Supported runtime roles

```text
ChatGPT
→ native daily learning runtime
→ best with GitHub connector / MCP / repository access

Claude
→ native daily learning runtime
→ best with project context, artifacts, and repository-assisted work

OpenHanako / HanaAgent
→ optional desktop enhanced runtime
→ local files, desks, skills, scheduled tasks, bridge channels, subagents

Claude Code / Codex / Cursor / CLI agents
→ deployment and source-code assistants for OpenHanako
→ not the maintained daily tutoring layer
```

The project should describe capabilities, not force one brand. It should also avoid pretending that every capable tool has the same permissions.

## Why memory matters

The AI should remember stable preferences only:

```text
Use GitLearnOS with one active learning runtime and one chosen state layer. Prefer GitHub as the state layer for native ChatGPT or Claude workflows. Treat local files as protected source material. Ask for local excerpts only when needed. Keep English and Chinese in separate files. Report every changed file.
```

Without memory or project instructions, the user has to repeat the same setup in every conversation.

## Minimum runtime

```text
one AI tool
+ one target GitHub repository or one accessible local state layer
+ one rule file
+ honest reporting
```

## Best native runtime

```text
one main native AI tool
+ GitHub repository connector
+ project memory or persistent instructions
+ clear permission boundary
+ optional local file upload when needed
```

## Local-first path

A local workspace can test or run the method, but local access is not the same as GitHub access.

Use local git or Obsidian only when the active runtime can actually access those files, or when the AI provides exact patches for the user to apply manually.

For the boundary, see [Local Runtime Note](local-runtime-note.md).
