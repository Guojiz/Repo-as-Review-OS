# AGENTS.md

[中文接手规则](AGENTS.zh-CN.md)

This file is for ChatGPT, Codex, Claude Code, Cursor, Windsurf, and other AI agents. Follow it before editing this repository or helping a user set up their own Repo as Review OS repository.

## Mission

Repo as Review OS is a goal-driven AI learning operating system built on GitHub.

Your job is to help users turn scattered learning materials into a structured repository with goals, source records, reusable models, review sets, spaced repetition, dashboards, automation outputs, and runtime rules.

## Read first

1. `README.md`
2. `START-HERE.md`
3. `OPERATING-MODEL.md`
4. `AGENT-RUNTIME.md`
5. `docs/skill-and-memory-runtime.md`
6. `skills/repo-as-review-os/SKILL.md` if the environment supports skills
7. Relevant files in `templates/`
8. Relevant demos in `examples/`

## Runtime rule

If the environment supports file-based skills, use:

```text
skills/repo-as-review-os/SKILL.md
```

If the environment does not support skills, use memory, custom instructions, project instructions, or repository-level instructions from:

```text
docs/skill-and-memory-runtime.md
```

Skill gives behavior. Memory gives stable preferences. Repository files store current learning state.

## Do

- Identify your permission level before making changes.
- Keep original sources traceable.
- Mark incomplete sources honestly.
- Keep summaries separate from full sources.
- Turn repeated mistakes or notes into reusable models.
- Add spaced-repetition fields when useful.
- Maintain dashboards and review sets.
- Keep English and Chinese in separate files when possible.
- Prefer small, reviewable changes.
- Explain changed files after editing.

## Do not

- Do not invent missing study context.
- Do not treat a summary as a source.
- Do not publish private examples.
- Do not upload copyrighted textbooks, test pages, teacher files, private screenshots, or real score reports into public repositories.
- Do not remove user data unless explicitly asked.
- Do not mix English and Chinese line by line in long documents.
- Do not optimize repository beauty at the cost of learning usefulness.

## New user repository setup

When helping a user create their own learning repository:

1. Confirm whether it is public or private.
2. Recommend private if it will contain real learning data.
3. Copy or recreate the core method files and templates.
4. Create `dashboard.md`.
5. Create `goals/main-goal.md`.
6. Create folders for sources, models, reviews, templates, agents, automations, and archive.
7. Add skill runtime or memory fallback instructions.
8. Report what was created.

## Output format

After work, report:

```text
Changed files:
- path: what changed

Still missing:
- item or source needed

Next action:
- recommended next step
```
