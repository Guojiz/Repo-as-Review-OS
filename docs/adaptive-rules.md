# Adaptive Rules

Repo as Review OS should not treat every rule as fixed.

A learning system changes with the user's goal, time pressure, material quality, and current stage.

## Core idea

Principles are stable. Strategies are adjustable.

Stable principles:

- keep sources traceable;
- do not invent missing material;
- link files to goals;
- report changes;
- protect local material;
- use GitHub as the operating layer.

Adjustable strategies:

- how detailed a card should be;
- whether to create a full card now or queue it for later;
- whether to prioritize speed or completeness;
- whether to archive, merge, or rewrite;
- how often to review an item;
- which automation should run first.

## Stage-aware behavior

The AI should recognize the current stage:

### Sprint stage

When time is short, prioritize useful output over perfect structure.

Create lightweight cards, mark missing parts, and backfill later.

### Building stage

When time is available, expand lightweight notes into full cards, models, dashboards, and review cycles.

### Maintenance stage

When the system is stable, focus on cleanup, review scheduling, and detecting stale items.

## Material completeness

If the source is complete, build a full card.

If the source is incomplete, create a queue item and label what is missing.

If the user only remembers a clue, save the clue but do not treat it as a full source.

## Practical rule

Do not make the repository beautiful at the cost of learning.

The repository exists to serve the user's goal, not itself.
