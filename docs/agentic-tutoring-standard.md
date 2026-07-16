# GitLearnOS Evaluation Standard

GitLearnOS is capability-benchmarked against HKU DeepTutor while remaining a lightweight toolkit for an external AI agent.

The standard is not feature parity. The standard is whether the toolkit preserves the learning-critical loop with far lower deployment cost and fully inspectable learner-owned state.

## Two evaluation layers

### Capability direction: DeepTutor

Use DeepTutor's public design as the reference for these questions:

1. Is learning grounded in accessible sources?
2. Does learner state evolve from interaction evidence?
3. Can weak points drive adapted questions?
4. Does the system close the loop from question to learner result to future behavior?
5. Is personalization inspectable rather than hidden?
6. Can tools and skills extend the learning workflow?

### Practical implementation: original repository behavior

Use the original `zhongkao` repository system to check:

1. Are files understandable to the learner and another agent?
2. Are mistakes turned into reusable recognition models?
3. Do old items return for review?
4. Does the dashboard lead to a concrete next action?
5. Are sources, summaries, and incomplete records kept distinct?
6. Can the system remain light enough to use every day?

## Acceptance tests

### A. Five-minute handoff

A new capable agent should read at most the entry rules and active target state, then answer:

- What is the active goal?
- What is due now?
- Which gap has evidence?
- What source or model supports the task?
- What should happen next?

Fail if the agent must read the entire template repository before acting.

### B. Real learning session

The system must be able to run:

```text
observable objective
→ learner attempt
→ diagnosis
→ adaptive support
→ fresh verification
→ evidence score
→ writeback
```

Fail if it only generates notes, folders, or generic worksheets.

### C. Evidence integrity

- A generated review is not marked complete before an attempt.
- Exposure or self-report alone does not produce `stable` or score 3.
- A learner-profile claim links to observable evidence.
- Contradictory evidence changes confidence instead of being silently discarded.

### D. Source integrity

- Full, excerpt, summary-only, local-only, missing, and uncertain sources remain distinct.
- The agent never invents unavailable source content.
- Public repositories contain only safe, cleaned examples.

### E. Adaptive practice

Practice is selected from active goals, due items, recent evidence, and knowledge gaps. Difficulty or support changes after observed performance.

Fail if practice is random, copied from a generic template, or disconnected from learner state.

### F. Deterministic review

An observed score maps to a reproducible next-review interval. A later agent can see why the date was chosen.

### G. Selective writeback

The repository records durable changes, not every chat turn. Session logs contain observable evidence and outcomes, not hidden reasoning or full private transcripts.

### H. Runtime honesty

The agent detects actual permissions and capabilities. It does not claim GitHub writeback, local-file reading, connected-source use, memory updates, or automation completion without performing them.

### I. Lightweight deployment

The basic loop must not require:

- a custom server;
- a database or vector store;
- GitHub Actions;
- API keys beyond the user's chosen AI environment;
- a desktop runtime;
- multi-agent orchestration;
- copying the whole template into the target repository.

### J. User control

The learner can inspect, edit, export, or move all canonical learning state. Destructive, visibility, privacy, secret, and license changes require explicit approval.

## Target quality levels

### Level 0 — archive

Files exist, but goals, evidence, and next actions are unclear.

### Level 1 — organized state

Goals, sources, models, gaps, and dashboard are connected.

### Level 2 — closed learning loop

The system elicits attempts, diagnoses gaps, scores observed evidence, schedules review, and updates state.

### Level 3 — adaptive continuity

Repeated evidence changes explanation style, difficulty, practice selection, and learner profile while remaining traceable.

Public alpha should reliably meet Level 2 in its main demo before claiming Level 3.

## Non-goals

GitLearnOS does not claim feature parity, benchmark-score parity, or runtime parity with DeepTutor. It is successful when it captures the learning-critical structure in a portable toolkit and an existing capable agent can execute it reliably.
