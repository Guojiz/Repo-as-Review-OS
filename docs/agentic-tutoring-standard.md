# GitLearnOS Evaluation Standard

GitLearnOS should first be judged against the original `zhongkao` learning repository system: can it preserve the learning loop, file discipline, review habits, AI handoff, and inspectable progress that made the original system useful?

External agentic tutoring research is useful as a reference signal, but it is not the primary benchmark and should not be used to overstate what this lightweight repository template can do.

The repository is still named `Repo-as-Review-OS` for continuity. The product concept is **GitLearnOS**.

## Primary baseline: the original zhongkao system

The first question is practical:

```text
Can GitLearnOS reproduce the useful behavior of the original zhongkao repository system with a lighter, reusable structure?
```

That means checking whether it can keep:

1. one durable GitHub learning workspace;
2. clear separation between template repository and personal target repository;
3. source records instead of vague memory;
4. reusable models extracted from mistakes or materials;
5. knowledge gaps that can drive later review;
6. review sets and spaced repetition fields;
7. a dashboard that tells the learner what to do next;
8. AI handoff notes that let another capable tool continue;
9. honest local-file boundaries;
10. readable Markdown files that the learner can inspect and edit.

For the detailed parity check, see [Parity with the Original System](parity-with-original-system.md).

## Secondary reference: agentic tutoring research

A serious AI learning system can learn from modern tutoring research, but GitLearnOS does not claim to reproduce a full tutoring platform.

Use these research-facing questions as design checks, not as product claims:

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

GitLearnOS answers these requirements with ordinary repository structure instead of a private tutoring runtime.

```text
Original zhongkao system behavior
→ reproduced as reusable GitHub structure

Unified learning context
→ one target GitHub repository

Source grounding
→ sources/ and source-status records

Learner state
→ dashboard.md, learner-profile.md, memory/GitHub sync notes

Mistake to model
→ models/ and reusable problem patterns

Knowledge gaps
→ knowledge-gaps/ linked to source, model, review, and dashboard entries

Practice from weak points
→ reviews/ and optional automations/practice-generator/

Critique and revision
→ lightweight Organizer + Critic + Revision routine

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

Do not turn GitLearnOS into a heavy tutoring runtime or a paper-shaped benchmark costume.

Avoid requiring:

- a database;
- a vector memory engine;
- a custom multi-agent server;
- a required desktop agent;
- a required local script;
- one specific AI product;
- uploading all textbooks into GitHub;
- pretending ChatGPT Project is a full learning repository;
- claiming parity with full tutoring platforms.

The standard is practical: preserve the original learning loop, make it reusable, and keep it light.

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
Original zhongkao system
→ real working learning loop
→ personalized, inspectable, GitHub-based

GitLearnOS
→ reusable template version
→ lighter personal learning substrate
→ open GitHub state
→ easier handoff across tools

Full tutoring platform
→ stronger packaged experience
→ heavier runtime
→ less direct control over the learning state
```

## Internal contradiction checks

These rules prevent the project from contradicting itself:

1. Use external research as reference, but do not make it the project's main identity.
2. Recommend ChatGPT and Claude, but do not make either mandatory.
3. Support single-context agents, but do not claim they have long-term memory.
4. Use ChatGPT Project for fixed materials, but do not treat it as the learning repository.
5. Use ChatGPT memory for stable preferences, but do not treat it as the source of truth.
6. Use GitHub as the durable state, but do not require all raw materials to be uploaded.
7. Allow desktop agents, Codex, or local tools, but do not require them by default.
8. Use automations, but do not claim prompt-only automations completed repository work.
9. Support visual/math explanations, but prefer built-in ChatGPT abilities before adding extra tooling.

## User-facing promise

GitLearnOS is for learners who want the useful loop of the original zhongkao-style learning repository without being locked into one exam, one AI product, or one local workflow.

It keeps the learning system readable:

```text
materials → models → knowledge gaps → reviews → dashboard → memory sync → next action
```

The user can see the files, inspect the history, switch AI tools, and keep learning without losing the thread.
