# AGENTS.md

[中文接手规则](AGENTS.zh-CN.md)

This file is for ChatGPT, Codex, Claude Code, Cursor, Windsurf, and other AI agents. Follow it before editing this repository or helping a user set up their own GitLearnOS repository.

## Mission

GitLearnOS is a lightweight learning-trace operating system for AI-assisted study, built on GitHub.

Your job is to help users turn scattered learning materials into a structured repository with goals, learner profile, source records, reusable models, knowledge gaps, review sets, spaced repetition, dashboards, automation outputs, and runtime rules.

## Read first

1. `README.md`
2. `START-HERE.md`
3. `QUICKSTART.md`
4. `docs/first-experiment-guide.md`
5. `docs/runtime-self-adaptation.md`
6. `docs/automation-runtime-matrix.md`
7. `docs/local-runtime-note.md`
8. `OPERATING-MODEL.md`
9. `AGENT-RUNTIME.md`
10. `docs/skill-and-memory-runtime.md`
11. `docs/adaptive-memory-and-learner-profile.md`
12. `docs/lightweight-skg-dpm.md`
13. `skills/repo-as-review-os/SKILL.md` if the environment supports skills
14. Relevant files in `templates/`
15. Relevant demos in `examples/`

## Runtime rule

Before acting, identify the current runtime:

```text
environment:
read access:
write access:
skill support:
memory or project-instruction fallback:
manual user steps needed:
```

If the environment supports file-based skills, use:

```text
skills/repo-as-review-os/SKILL.md
```

If the environment does not support skills, use memory, custom instructions, project instructions, or repository-level instructions from:

```text
docs/skill-and-memory-runtime.md
```

Skill gives behavior. Memory gives stable preferences. Repository files store current learning state.

## Repository roles

When helping a new user, keep these roles separate:

```text
Repo-as-Review-OS repository
→ template repository
→ method, docs, skills, examples, rules

User target repository
→ personal GitLearnOS repository
→ goals, learner profile, sources, models, knowledge gaps, reviews, dashboard
```

Do not write personal learning data into the template repository.

## Do

- Identify your permission level before making changes.
- Keep template repository and target learning repository separate.
- Ask the user to complete manual app, connector, project, or permission steps when needed.
- Keep original sources traceable.
- Mark incomplete sources honestly.
- Keep summaries separate from full sources.
- Turn repeated mistakes or notes into reusable models.
- Record knowledge gaps when a model or practice result exposes one.
- Add spaced-repetition fields when useful.
- Maintain dashboards and review sets.
- Keep English and Chinese in separate files when possible.
- Prefer small, reviewable changes.
- Explain changed files after editing.

## Do not

- Do not invent missing study context.
- Do not treat a summary as a source.
- Do not publish private examples.
- Do not upload protected or private learning materials into public repositories.
- Do not remove user data unless explicitly asked.
- Do not mix English and Chinese line by line in long documents.
- Do not optimize repository beauty at the cost of learning usefulness.
- Do not require GitHub Actions or API keys for basic setup.

## New user repository setup

When helping a user create their own learning repository:

1. Confirm the template repository and target repository.
2. Check whether the target repository is empty or already has files.
3. Confirm whether it is public or private.
4. Recommend private if it will contain real learning data.
5. Copy or recreate the core method files and templates in the target repository.
6. Create `dashboard.md`.
7. Create `learner-profile.md`.
8. Create `goals/main-goal.md`.
9. Create folders for sources, models, knowledge-gaps, reviews, templates, agents, automations, and archive.
10. Add skill runtime or memory fallback instructions.
11. Ask for the user's first learning goal.
12. Report what was created.

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