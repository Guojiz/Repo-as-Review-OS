# Start Here

GitLearnOS is a lightweight learning-trace operating system for AI-assisted study, built on GitHub.

It helps a user and an AI tool turn scattered learning materials into a writable, traceable, and reviewable learning repository.

## Copy this to an AI tool

```text
Read this repository: https://github.com/Guojiz/Repo-as-Review-OS

The repository is named Repo-as-Review-OS for continuity. The product concept is GitLearnOS.

Start with START-HERE.md, README.md, QUICKSTART.md, AGENT-RUNTIME.md, AGENTS.md, docs/runtime-self-adaptation.md, docs/skill-and-memory-runtime.md, docs/adaptive-memory-and-learner-profile.md, and docs/source-and-learner-state.md. Follow linked documents only when they are relevant to your current runtime.

Help me build my own GitLearnOS. First explain what it is, then identify your current runtime, memory capability, permission boundary, GitHub access, and any manual steps I must complete. Then guide me to create or choose one target GitHub repository.

Treat this Repo-as-Review-OS repository as the template repository. Treat my target repository as the personal learning repository. Do not write my learning data into the template repository.

If your environment supports skills, use skills/repo-as-review-os/SKILL.md. If it does not support skills, use the memory fallback in docs/skill-and-memory-runtime.md.

After that, create goal files, learner-profile.md, folder structure, source rules, model templates, knowledge-gap fields, spaced-repetition fields, automation output folders, and a dashboard in my target repository. If I already gave a learning goal, use it. If not, ask me for my first learning goal. Report every file created or edited.
```

## What the AI should do

1. Read this file.
2. Read `README.md`.
3. Read `QUICKSTART.md`.
4. Read `docs/runtime-self-adaptation.md`.
5. Read `AGENT-RUNTIME.md`.
6. Read `AGENTS.md`.
7. Read `docs/skill-and-memory-runtime.md`.
8. Read `docs/adaptive-memory-and-learner-profile.md`.
9. Read `docs/source-and-learner-state.md`.
10. Explain the system to the user.
11. Identify the current runtime, memory capability, file access, and permission boundary.
12. Separate the template repository from the target learning repository.
13. Help the user create or choose one target GitHub repository.
14. Decide whether to use skill runtime, native memory, project instructions, or a single-context fallback.
15. Build the folder structure, templates, goal file, learner profile, knowledge-gap records, dashboard, and runtime rules in the target repository.
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
- learner profile;
- source records;
- reusable models;
- knowledge gaps;
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
docs/adaptive-memory-and-learner-profile.md
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
