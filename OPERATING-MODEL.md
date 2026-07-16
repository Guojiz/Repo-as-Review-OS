# Operating Model

GitLearnOS is a learner-owned control layer. It does not own the place where learning happens; one replaceable main agent organizes distributed input, generates targeted questions, and maintains durable state.

## Four layers

```text
real learning channels
→ teacher, class, tutoring, paper, books, platforms, exams, peers, AI

one main AI agent
→ identify intent, organize, question, act, explain, verify

GitLearnOS rules, skills, and learning-policy
→ govern provenance, automation, writeback, safety, and evidence

target GitHub repository
→ root shared policy and cross-subject view
→ subjects/<subject>/ for focused, inspectable learning state
```

Do not split these layers or responsibilities into mandatory agents.

## Three core capabilities

### Automatic organization

```text
new input
→ mark channel and provenance
→ connect goal and gap
→ deduplicate and extract
→ update resolution state
→ surface the next action
```

### Targeted question generation

```text
goal + source/model + gap + prior performance + learner constraints
→ diagnostic / practice / variation / transfer / review / external question pack
→ answer or rubric
→ result writeback
```

### Automated execution

```text
learner event or agent handoff
→ read learning-policy
→ perform safe, low-risk, reversible actions
→ atomic writeback and deduplication
→ refresh dashboard
→ return a transparent receipt
```

Background scheduling is enabled only when the current runtime has a real scheduler.

## Two loops

Cross-channel coordination is the primary loop:

```text
capture
→ connect
→ route to teacher, learner, AI, or another channel
→ organize feedback or generate questions
→ write back
→ next action
```

AI tutoring is optional:

```text
attempt
→ diagnose
→ support
→ fresh verification
→ score
→ review
```

## State model

- `learning-policy.md`: automation, privacy, writeback, and scheduling preferences;
- `dashboard.md`: priorities, due work, waiting feedback, and next action;
- `learner-profile.md`: durable evidence-backed learner state;
- `subjects/<subject>/goals/`: subject outcomes and success criteria;
- `subjects/<subject>/inbox/`: quick input not yet fully processed;
- `subjects/<subject>/sources/`: teacher, class, book, platform, AI, and other provenance;
- `subjects/<subject>/models/`: reusable understanding reconciled across sources;
- `subjects/<subject>/knowledge-gaps/`: resolution lifecycle and mastery evidence;
- `subjects/<subject>/handoffs/`: question and feedback packs for teachers, peers, or other agents;
- `subjects/<subject>/reviews/`: generated questions, answers, scores, and next dates;
- `subjects/<subject>/sessions/`: material cross-channel activities that changed state.

The agent routes each event to a subject automatically. Root files coordinate subjects; they do not duplicate subject state. Create only folders required by the current event.

## Decision rules

Before writing, ask internally:

```text
Did the learner provide or authorize this?
Does it serve an active goal?
Is there one canonical owner for the state?
Will it have future value?
Is the action safe, low-risk, and reversible?
```

Keep temporary content out of the repository. Under `safe-auto`, perform safe actions and report; ask before high-impact actions.

## External resolution and mastery

Resolution state and mastery evidence are separate. A teacher's answer may immediately end waiting and redundant AI teaching; independent mastery may still be checked through performance, delayed recall, or transfer. The learner may opt out of verification.

## Product boundary

GitLearnOS keeps grounded sources, evolving learner state, targeted questions, feedback reconciliation, and learner-controlled automation in a small file-based control layer.

It intentionally omits a full app, server, mandatory multi-agent runtime, RAG engine, and database.
