# Product Positioning

GitLearnOS is a lightweight, learner-owned learning control layer for one capable, replaceable AI agent and one GitHub repository.

It automatically organizes learning from any channel, generates targeted questions, and writes durable state back under learner-defined policy. It is not a standalone tutoring platform, a ChatGPT-only project, an Obsidian workflow, or a multi-agent framework.

## One sentence

```text
Organize learning from anywhere, generate the next useful questions, and keep learner-owned state in sync.
```

## Product thesis

Learning is already distributed across teachers, class, tutoring, paper, books, practice platforms, peers, and AI. A useful lightweight system should coordinate those channels without forcing them into its own runtime.

GitLearnOS therefore treats:

- one repository as the learner-owned control plane;
- root files as shared policy and cross-subject coordination;
- `subjects/<subject>/` as focused subject state;
- the current AI as a replaceable operator;
- human teachers and external platforms as first-class channels;
- organization and question generation as core capabilities;
- live AI tutoring as one optional route.

School and self-study share learner-level preferences while preserving different goals, deadlines, methods, and evidence. The same system adapts to remediation, exams, exploration, advanced study, projects, research, and practical skills.

## Three core capabilities

| Capability | Product promise |
|---|---|
| organize | capture, classify, route by subject, connect, deduplicate, reconcile, and surface the next action |
| question | generate grounded diagnostic, practice, variation, transfer, review, and help-seeking questions |
| automate | execute safe writeback and scheduling with transparent receipts, idempotence, and undo |

Explanation, search, scoring, spaced repetition, and learner modeling support these capabilities.

## Lightweight implementation

| Learning need | GitLearnOS implementation |
|---|---|
| cross-channel capture | subject inbox, source records, activity records |
| focused context | one repository with `subjects/<subject>/` folders |
| learner control | root learning policy, Markdown, Git history, undo |
| organization | automatic subject routing, canonical state ownership, dashboard |
| personalized questions | question skill, reviews, handoff packs |
| teacher coordination | gap lifecycle, handoffs, feedback reconciliation |
| mastery evidence | learner results, support level, delayed and transfer checks |
| automation | immediate and on-handoff rules; optional real scheduler |
| extensibility | one portable router and focused `SKILL.md` workflows |

## Why GitHub

GitHub provides stable paths, explicit ownership, version history, inspectable evidence, portability across AI runtimes, and recovery from agent mistakes.

The repository is passive state plus declarative policy. The active agent performs organization, question generation, tutoring when requested, and writeback. Scheduled background behavior is optional and runtime-dependent.

## Why one repository with subject folders

One repository keeps permission, backup, policy, and learner control simple. Subject folders reduce irrelevant context and prevent mathematics, languages, coding, and other learning state from becoming one undifferentiated pile.

The agent infers the subject, asks only when a wrong write is plausible, and honors natural-language corrections. It creates the active subject and the first useful file—not an empty taxonomy.

See [Subject Folder Model](subject-folder-model.md).

## Why one main agent

Modern tool-capable runtimes can read connected state, reason across files, act, and verify within one workspace. GitLearnOS uses that as the standard: one capable main agent loads only the relevant workflow.

Mandatory multi-agent orchestration would add handoff cost and is unnecessary for the lightweight product.

## Appropriate users

GitLearnOS fits a learner who:

- learns across teachers, school, self-study, paper, platforms, and AI;
- wants AI to reduce organization and review overhead;
- wants questions based on personal state rather than generic worksheets;
- values readable, portable, self-owned records;
- does not want to deploy another platform.

## Product boundary

Minimum:

```text
one capable main agent
+ one private repository with one active subject folder
+ GitLearnOS rules
+ one learning goal or input
```

Optional connected files, web research, code execution, visualization, native memory, and real schedulers may improve execution. None is required for the basic control layer.

## Promise

Success is not repository size, number of generated documents, or time spent talking to AI. Success means the learner can report an event once, receive useful organization or questions, and trust that the resulting state is correctly routed, updated, visible, portable, and reversible.
