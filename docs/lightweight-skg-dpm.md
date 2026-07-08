# Lightweight SKG and DPM

GitLearnOS uses a lightweight version of two personalization ideas:

```text
Static knowledge grounding
→ relatively stable source and model layer

Dynamic personal memory
→ changing learner state and memory layer
```

The names here are implementation concepts, not required platform components.

## Static layer: source and model grounding

The static layer is the part that should not change too quickly.

In GitLearnOS, it is usually:

```text
local textbooks / PDFs / screenshots / original files
+ sources/
+ models/
+ knowledge-gaps/
+ source-status records
+ Git history
```

This layer answers:

```text
What material is this based on?
Which source did the AI use?
Which concept or problem model was extracted?
Which knowledge gap was found?
Can the learner inspect the evidence?
```

Local folders may keep the full textbook or original file. GitHub keeps the source record, selected excerpts, summaries, model cards, knowledge-gap records, and links.

## Dynamic layer: learner profile and memory

The dynamic layer changes as the learner studies.

In GitLearnOS, it is usually:

```text
learner-profile.md
+ knowledge-gaps/
+ reviews/
+ automations/organizer-critic/
+ ChatGPT or Claude memory when available
+ optional external memory tools for recall
```

This layer answers:

```text
What is the learner trying to do now?
What knowledge gaps are active?
What explanation style works better?
What has improved?
What should be reviewed next?
```

## Active and passive relation

Native AI memory is active. It may surface automatically.

GitHub is passive. The AI must read or search it.

Local files are protected source material. The AI should not pretend it has read them unless it actually has access.

```text
native memory
→ active preference cache

GitHub repository
→ passive but inspectable source of truth

local folders
→ protected original source layer

learner-profile.md
→ bridge between active memory and passive repository state
```

## Personalized question generation

Personalized practice should come from the learner's actual repository state, not from a generic quiz template.

Default input:

```text
recently split models
+ active knowledge gaps
+ learner-profile.md
+ source records
+ review schedule
```

Default output:

```text
small practice set
+ answer
+ explanation
+ linked source/model/gap/profile entry
+ next review date
```

## Closed loop

GitLearnOS keeps the loop simple:

```text
source
→ split into model
→ identify knowledge gap
→ generate personalized question
→ learner result
→ update learner-profile.md
→ schedule next review
→ refine future questions
```

This is the core tutoring loop. It can run in ChatGPT, Claude, a single-context AI tool, Codex, or a local agent as long as the tool respects the repository state and its actual permissions.

## Rule

Do not make this heavier than necessary.

The repository should stay readable. The learner should be able to open the files and understand why the AI made a decision.