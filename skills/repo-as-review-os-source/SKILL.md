---
name: repo-as-review-os-source
description: Use when turning learning materials, notes, paper references, practice results, or mistakes into honest source records in a Repo as Review OS repository. This skill prevents summaries from being treated as full sources and labels missing material clearly.
---

# Repo as Review OS Source Skill

## Purpose

Use this skill to handle learning sources safely and honestly.

A source can be a note, practice result, mistake record, paper reference, class material, or user explanation.

## When to use

Use when the user provides or mentions:

- a learning note;
- a mistake;
- a paper or article;
- a class material reference;
- a practice result;
- a partial memory of a question;
- a local source that the AI cannot fully access.

## Core rule

Never treat a summary as a full source.

Never invent missing text, diagrams, answer choices, paper sections, or unavailable material.

## Source workflow

```text
material arrives
→ identify source type
→ check completeness
→ create source record
→ label missing parts
→ decide whether to extract a model
→ link source to goal or dashboard
```

## Source status labels

Use these labels when helpful:

```text
full-source
summary-only
local-only-source
needs-source
needs-clear-source
not-full-solution
draft-full
source-record
```

## Minimal source record

A source record should include:

```text
status
source type
goal link
source availability
what is known
what is missing
what can be extracted
AI rule
```

## Public repository rule

For public repositories, use cleaned or fictional examples.

For real learning records, recommend a private repository.

## Output standard

```text
Changed files:
- source record path: what was recorded

Still missing:
- missing source details

Next action:
- extract model / ask user for clearer source / schedule review
```
