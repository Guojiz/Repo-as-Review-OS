# Start Here

Repo as Review OS is a goal-driven AI learning operating system built on GitHub.

It helps a user and an AI tool turn scattered learning materials into a writable, traceable, and reviewable learning repository.

## Copy this to an AI tool

```text
Read this repository: https://github.com/Guojiz/Repo-as-Review-OS
Start with START-HERE.md, README.md, QUICKSTART.md, docs/first-experiment-guide.md, docs/runtime-self-adaptation.md, OPERATING-MODEL.md, AGENT-RUNTIME.md, AGENTS.md, and docs/skill-and-memory-runtime.md. Then inspect examples/en/demo-research-reading-lite, examples/en/demo-sat-lite, and examples/zh-CN/demo-zhongkao-lite.

Help me build my own Review OS. First explain what it is, then identify your current runtime, permission boundary, and any manual steps I must complete. Then guide me to create or choose one target GitHub repository.

Treat this Repo as Review OS repository as the template repository. Treat my target repository as the personal learning repository. Do not write my learning data into the template repository.

If your environment supports skills, use skills/repo-as-review-os/SKILL.md. If it does not support skills, use the memory fallback in docs/skill-and-memory-runtime.md.

After that, create goal files, folder structure, source rules, model templates, spaced-repetition fields, automation output folders, and a dashboard in my target repository. Report every file created or edited.
```

## What the AI should do

1. Read this file.
2. Read `README.md`.
3. Read `QUICKSTART.md`.
4. Read `docs/first-experiment-guide.md`.
5. Read `docs/runtime-self-adaptation.md`.
6. Read `OPERATING-MODEL.md`.
7. Read `AGENT-RUNTIME.md`.
8. Read `AGENTS.md`.
9. Read `docs/skill-and-memory-runtime.md`.
10. Explain the system to the user.
11. Identify the current runtime and permission boundary.
12. Separate the template repository from the target learning repository.
13. Help the user create or choose one target GitHub repository.
14. Decide whether to use skill runtime or memory fallback.
15. Build the folder structure, templates, goal file, dashboard, and runtime rules in the target repository.
16. Report every file created or edited.

## What the human should do

1. Create or choose one target GitHub repository for personal learning data.
2. Connect the AI tool to that repository through MCP, a GitHub connector, or another safe integration.
3. Use a private repository for real learning data.
4. Keep protected or private materials local unless a small excerpt is needed.
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

Before choosing a runtime path, read:

```text
docs/runtime-self-adaptation.md
docs/automation-runtime-matrix.md
```

If the AI tool supports skills, use:

```text
skills/repo-as-review-os/SKILL.md
```

If the AI tool does not support skills, use:

```text
docs/skill-and-memory-runtime.md
```

Skill gives the AI behavior. Memory gives the AI stable preferences. The repository gives the AI current learning state.
