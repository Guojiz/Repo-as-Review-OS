---
name: repo-as-review-os-model
description: Use when extracting reusable learning models from mistakes, notes, examples, paper claims, or repeated patterns in a Repo as Review OS repository. This skill turns isolated learning events into models that can be reviewed and reused.
---

# Repo as Review OS Model Skill

## Purpose

Use this skill to turn a source record, mistake, note, or repeated pattern into a reusable learning model.

A model is not a summary. It is a portable way to recognize and solve similar future problems.

## When to use

Use when the user asks to:

- summarize the lesson from a mistake;
- turn a question into a model;
- extract a method;
- compare examples;
- build a reusable pattern;
- convert reading notes into concepts;
- preserve a trick, rule, or workflow.

## Model workflow

```text
source record
→ identify repeated pattern
→ name the model
→ write recognition cues
→ write method
→ write traps
→ write next-time reaction
→ add review fields
→ link back to source and goal
```

## Minimal model file

A model should include:

```text
status: model
goal link
source link
first learned
last reviewed
next review
review count
memory status
recognition cue
method
common trap
next-time reaction
review note
```

## Good model test

A model is useful if the user can answer:

```text
When should I recognize this?
What should I do next time?
What mistake does this prevent?
How will I review it later?
```

## Bad model signs

Avoid models that are only:

- a copied answer;
- a vague summary;
- a beautiful title without method;
- an explanation with no review plan;
- a rule that cannot be recognized in future tasks.

## Output standard

```text
Changed files:
- model path: what model was created or updated

Still missing:
- source or example needed

Next action:
- generate review / link to dashboard / ask for another example
```
