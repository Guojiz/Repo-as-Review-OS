---
name: repo-as-review-os-source
description: Turn learning material, references, mistakes, or incomplete recollections into traceable GitLearnOS source records without pretending that summaries or unavailable originals are complete sources.
---

# GitLearnOS Source Handling

## Source states

Use one:

- `full`: the agent can inspect the complete authorized source;
- `excerpt`: only a bounded excerpt is available;
- `summary-only`: a summary exists but not the source;
- `local-only`: the original exists outside current access;
- `missing`: the source is referenced but unavailable;
- `uncertain`: provenance or completeness is unclear.

## Workflow

```text
material arrives
→ identify provenance and access
→ link it to a goal
→ record what is actually available
→ separate observation from interpretation
→ choose one extraction target
→ route to session or model only when justified
```

## Required record fields

- status and source type;
- title/reference or stable locator;
- goal link;
- access/completeness state;
- inspected portion;
- known facts or learner event;
- missing material;
- permitted use and privacy boundary;
- next learning action.

## Integrity rules

- Never reconstruct unavailable wording, answer choices, figures, data, or citations.
- Never relabel a summary as a full source.
- A learner's memory of a problem is evidence of the learning event, not necessarily the original problem.
- Keep private or copyrighted originals out of public repositories.
- Store only the minimum excerpt needed for future learning.

## Output

```text
Source state:
Changed files:
Missing material:
Safe extraction target:
Next action:
```
