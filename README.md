# Repo as Review OS
<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/5e1942dd-5996-4346-ba3c-3afe18d5503d" />


[中文说明](README.zh-CN.md)
<p align="center">
  <a href="https://github.com/Guojiz/Repo-as-Review-OS/stargazers">
    <img src="https://img.shields.io/github/stars/Guojiz/Repo-as-Review-OS?style=flat-square" alt="Stars"/>
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-green.svg?style=flat-square" alt="License: MIT"/>
  </a>
</p>
**Repo as Review OS is a goal-driven AI learning operating system built on GitHub.**

It is not just a review template. It turns one GitHub repository into a writable learning timeline that an AI tool can read, edit, track, organize, generate practice from, and maintain over time.

Current status: public alpha. See `PUBLIC-ALPHA.md`.

New here? Start with `QUICKSTART.md`.

Core model:

```text
goal
→ source
→ split
→ model
→ practice set
→ spaced repetition
→ automation
→ new understanding
```

## See the demos first

English research reading demo: `examples/en/demo-research-reading-lite/`

English SAT prep demo: `examples/en/demo-sat-lite/`

Chinese exam-math demo: `examples/zh-CN/demo-zhongkao-lite/`

They show how a learning goal becomes:

```text
main goal
→ source record
→ reusable model
→ review set
→ dashboard
→ next review
```

## Copy this to an AI tool

```text
Read this repository: https://github.com/Guojiz/Repo-as-Review-OS
Start with QUICKSTART.md, OPERATING-MODEL.md, START-HERE.md, AGENT-RUNTIME.md, AGENTS.md, skills/README.md, and docs/skill-and-memory-runtime.md. Then inspect examples/en/demo-research-reading-lite, examples/en/demo-sat-lite, and examples/zh-CN/demo-zhongkao-lite. Help me build my own Review OS. First explain what it is, then identify your permission boundary, then guide me to create or choose one GitHub repository. If your environment supports skills, start with skills/repo-as-review-os/SKILL.md and use the specific subskills when appropriate. If not, use the memory fallback in docs/skill-and-memory-runtime.md. After that, create goal files, folder structure, source rules, problem-model templates, spaced-repetition fields, automation output folders, and a dashboard.
```

## Why GitHub

GitHub is not just storage. It is a writable timeline.

It gives the AI:

- a file tree;
- writeback;
- history;
- timestamps;
- traceable changes;
- automation outputs;
- a durable workspace beyond one chat.

A normal AI project can store instructions and context, but it does not provide the same open file system, structured writeback, version history, and portable learning state.

## What the AI should do

1. Identify its permission level.
2. Read the user's goal.
3. Check the repository structure.
4. Find active sources, models, and weak points.
5. Decide what should be split, merged, rewritten, reviewed, generated, or archived.
6. Update files.
7. Schedule review if needed.
8. Report every change.

## Skill or memory runtime

If the AI tool supports skills, start with the router skill:

```text
skills/repo-as-review-os/SKILL.md
```

For the full skill suite, see:

```text
skills/README.md
```

If the AI tool does not support skills, use the memory or project-instruction fallback in:

```text
docs/skill-and-memory-runtime.md
```

Skill gives the AI behavior. Memory gives the AI stable preferences. The repository gives the AI current learning state.

## Human role

- Use a private repository for real study records.
- Use only cleaned examples in public templates.
- Grant one-repository access first, not broad account access.
- Keep textbooks, PDFs, screenshots, and private files local unless a small excerpt is needed.
- Require the AI to report every file it creates or edits.

## Contributing

Contributions are welcome: demos, templates, translations, automation prompts, documentation improvements, and feedback from trying the system with an AI tool.

Please read:

```text
CONTRIBUTING.md
PUBLIC-CHECKLIST.md
```

Use GitHub Issues to submit feedback, demo ideas, or bug reports.

## Key documents

```text
QUICKSTART.md                   Five-minute setup
OPERATING-MODEL.md              Overall operating model
AGENT-RUNTIME.md                Runtime guide for AI tools
skills/README.md                Skill suite overview
skills/repo-as-review-os/SKILL.md Main router skill
docs/skill-and-memory-runtime.md Skill and memory runtime guide
PUBLIC-ALPHA.md                 Public alpha note
PUBLIC-CHECKLIST.md             Public release checklist
CONTRIBUTING.md                 Contribution guide
examples/en/demo-research-reading-lite/ English research reading demo
examples/en/demo-sat-lite/      English SAT prep demo
examples/zh-CN/demo-zhongkao-lite/ Chinese exam-math demo
docs/product-positioning.md     Product positioning
docs/why-github.md              Why GitHub
docs/goal-model.md              Goal model
docs/adaptive-rules.md          Adaptive rules
docs/spaced-repetition.md       Spaced repetition
docs/filesystem-design.md       Filesystem design
docs/automation-model.md        Automation model
docs/lessons-from-original-system.md Lessons from the original system
```

## Suggested layout

```text
review-os/
├── dashboard.md
├── goals/
├── inbox/
├── sources/
├── models/
├── reviews/
├── templates/
├── agents/
├── automations/
└── archive/
```

## For AI agents

Read `QUICKSTART.md`, `OPERATING-MODEL.md`, `AGENT-RUNTIME.md`, `skills/README.md`, `docs/skill-and-memory-runtime.md`, and `AGENTS.md` before changing files.

## License

MIT License. See `LICENSE`.
