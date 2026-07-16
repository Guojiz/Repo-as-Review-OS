# Operating Model

GitLearnOS is a lightweight tutoring toolkit that separates active intelligence from durable learning state.

## Three layers

```text
active AI runtime
→ teaches, searches, questions, observes, and acts

GitLearnOS skills and rules
→ enforce the learning loop, evidence standard, and writeback policy

target GitHub repository
→ stores learner-owned, inspectable state and history
```

## Core loop

```text
goal
→ source or prior model
→ learner attempt
→ diagnosed gap
→ adaptive support
→ fresh verification
→ evidence score
→ selective writeback
→ next review or action
```

## State model

- `dashboard.md`: current linked view and next action;
- `learner-profile.md`: durable learner state supported by evidence;
- `goals/`: outcomes and success criteria;
- `sources/`: provenance, access, and inspected material;
- `models/`: reusable understanding;
- `knowledge-gaps/`: observable weaknesses and resolution rules;
- `reviews/`: prompts, responses, scores, and next dates;
- `sessions/`: concise material evidence when a session changes state.

## Decision rule

Before creating or editing a file, ask:

```text
Does this serve an active goal?
Is it grounded in available evidence?
Will it have future learning value?
Does a canonical file already own this state?
```

If not, keep it in the current conversation or do not create it.

## Benchmark boundary

DeepTutor supplies the capability direction: grounded sources, evolving learner state, personalized tasks, and a closed tutoring loop. GitLearnOS compresses that direction into portable files and skills operated by an external agent.

The system intentionally does not supply a full app, server, multi-agent runtime, RAG engine, or database.

## Minimum viable system

```text
one capable AI agent
+ one private target repository
+ one active goal
+ canonical agent rules
= enough to begin
```

Everything else is added when it improves learning.
