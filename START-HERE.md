# Start Here

Repo as Review OS is a goal-driven AI learning operating system built on GitHub.

It helps a user and an AI tool turn scattered learning materials into a writable, traceable, and reviewable learning repository.

## Copy this to an AI tool

```text
Read this repository: https://github.com/Guojiz/Repo-as-Review-OS
Start with START-HERE.md, README.md, OPERATING-MODEL.md, AGENT-RUNTIME.md, AGENTS.md, and docs/skill-and-memory-runtime.md. Then inspect examples/en/demo-research-reading-lite, examples/en/demo-sat-lite, and examples/zh-CN/demo-zhongkao-lite. Help me build my own Review OS. First explain what it is, then identify your permission boundary, then guide me to create or choose one GitHub repository. If your environment supports skills, use skills/repo-as-review-os/SKILL.md. If it does not support skills, use the memory fallback in docs/skill-and-memory-runtime.md. After that, create goal files, folder structure, source rules, model templates, spaced-repetition fields, automation output folders, and a dashboard.
```

## What the AI should do

1. Read this file.
2. Read `README.md`.
3. Read `OPERATING-MODEL.md`.
4. Read `AGENT-RUNTIME.md`.
5. Read `AGENTS.md`.
6. Read `docs/skill-and-memory-runtime.md`.
7. Explain the system to the user.
8. Identify the current permission boundary.
9. Help the user create or choose one GitHub repository.
10. Decide whether to use skill runtime or memory fallback.
11. Build the folder structure, templates, goal file, dashboard, and runtime rules.
12. Report every file created or edited.

## What the human should do

1. Create or choose one GitHub repository.
2. Connect the AI tool to that repository through MCP, a GitHub connector, or another safe integration.
3. Use a private repository for real learning data.
4. Keep copyrighted or private materials local unless a small excerpt is needed.
5. Ask the AI to report every change.

## Core idea

A repository can become the operating system for learning.

It should contain:

- goals;
- source records;
- reusable models;
- review sets;
- spaced repetition fields;
- dashboards;
- automation outputs;
- agent runtime rules;
- skill or memory fallback instructions.

## Runtime choices

If the AI tool supports skills, use:

```text
skills/repo-as-review-os/SKILL.md
```

If the AI tool does not support skills, use:

```text
docs/skill-and-memory-runtime.md
```

Skill gives the AI behavior. Memory gives the AI stable preferences. The repository gives the AI current learning state.
