# Agentic Tutoring Standard

GitLearnOS should be judged against the strongest open agentic tutoring systems, not against ordinary note templates.

This document defines the standard used to inspect this project.

The goal is not to copy a full tutoring platform. The goal is to preserve the useful learning loop in a lighter GitHub-native form.

The repository is still named `Repo-as-Review-OS` for continuity. The product concept is **GitLearnOS**.

## Benchmark standard

A serious AI learning system should answer these questions:

1. Does it keep a unified learning context?
2. Does it ground answers in sources instead of vague memory?
3. Does it maintain a learner state or profile?
4. Does it turn mistakes into reusable models?
5. Does it generate practice from weak points?
6. Does it critique and revise weak outputs?
7. Does it support writing as a learning surface?
8. Does it support visual or math explanations when useful?
9. Does it support review and repetition?
10. Can another AI tool take over the same learning state?
11. Can the learner inspect and edit the system?
12. Does it avoid pretending that unavailable tools or files were used?

## GitLearnOS answer

GitLearnOS answers these requirements with ordinary repository structure instead of a private runtime.

```text
Unified learning context
→ one target GitHub repository

Source grounding
→ sources/ and source-status records

Learner state
→ dashboard.md, optional learner-profile.md, memory/GitHub sync notes

Mistake to model
→ models/ and reusable problem patterns

Practice from weak points
→ reviews/ and automations/practice-generator/

Critique and revision
→ Organizer + Critic + Revision automation

Writing surface
→ writing files, drafts, README work, essays, reports, and revision notes

Visual and math explanations
→ ChatGPT built-in visual/code abilities, Desmos-ready expressions, HTML demos, or Python artifacts when useful

Review and repetition
→ spaced repetition fields and review schedule records

Cross-agent handoff
→ GitHub repository as the shared state

Inspectability
→ Markdown files and Git history

Honest boundaries
→ runtime checks before claiming repository access, local-file access, or completed automation
```

## What this project should not become

Do not turn GitLearnOS into a heavy tutoring runtime.

Avoid requiring:

- a database;
- a vector memory engine;
- a custom multi-agent server;
- a required desktop agent;
- a required local script;
- one specific AI product;
- uploading all textbooks into GitHub;
- pretending ChatGPT Project is a full learning repository.

The standard is high, but the implementation should remain light.

## Why a user might choose this instead of a full tutoring platform

A full tutoring platform is better when the user wants a packaged app, built-in runtime, integrated memory system, and managed tutoring interface.

GitLearnOS is better when the user wants:

- a lightweight setup;
- GitHub-native files and history;
- direct control over the learning structure;
- portability across ChatGPT, Claude, Zhipu, Codex, local agents, or future tools;
- private learning data stored in the user's own repository;
- no lock-in to a single tutoring app;
- a system that can be inspected, forked, simplified, or rebuilt by any capable AI.

In short:

```text
Full tutoring platform
→ stronger packaged experience
→ more built-in features
→ heavier runtime

GitLearnOS
→ lighter personal learning substrate
→ open GitHub state
→ easier handoff across tools
```

## Internal contradiction checks

These rules prevent the project from contradicting itself:

1. Recommend ChatGPT and Claude, but do not make either mandatory.
2. Support single-context agents, but do not claim they have long-term memory.
3. Use ChatGPT Project for fixed materials, but do not treat it as the learning repository.
4. Use ChatGPT memory for stable preferences, but do not treat it as the source of truth.
5. Use GitHub as the durable state, but do not require all raw materials to be uploaded.
6. Allow desktop agents, Codex, or local tools, but do not require them by default.
7. Use automations, but do not claim prompt-only automations completed repository work.
8. Support visual/math explanations, but prefer built-in ChatGPT abilities before adding extra tooling.

## User-facing promise

GitLearnOS is for learners who want the core loop of personalized AI tutoring without adopting a full tutoring platform.

It keeps the learning system readable:

```text
materials → models → reviews → dashboard → memory sync → next action
```

The user can see the files, inspect the history, switch AI tools, and keep learning without losing the thread.
