# Product Positioning

GitLearnOS is a lightweight, learner-owned learning control layer for one capable, replaceable AI agent and one GitHub repository.

It automatically organizes learning from any channel, generates targeted questions, and writes durable state back under learner-defined policy. It is not a standalone tutoring platform, a ChatGPT-only project, an Obsidian workflow, or a multi-agent framework.

## One sentence

```text
Organize learning from anywhere, generate the next useful questions, and keep learner-owned state in sync.
```

## Product thesis

Learning is already distributed across teachers, class, tutoring, paper, books, practice platforms, peers, and AI. A useful lightweight system should not force all activity into its own runtime.

GitLearnOS therefore treats:

- the repository as the learner-owned control plane;
- the current AI as a replaceable operator;
- human teachers and external platforms as first-class channels;
- organization and question generation as core capabilities;
- live AI tutoring as one optional route.

It preserves two goal tracks—school and self-study—that share knowledge state while using different deadlines, formats, and success criteria. Within either track, the need may be remediation, exam preparation, exploration, advanced study, project work, research, or practical skill. GitLearnOS adapts the output and evidence contract rather than creating a separate platform for every case.

## Three core capabilities

| Capability | Product promise |
|---|---|
| organize | capture, classify, connect, deduplicate, reconcile, and surface the next action |
| question | generate grounded diagnostic, practice, variation, transfer, review, and help-seeking questions |
| automate | execute safe writeback and scheduling with transparent receipts, idempotence, and undo |

Explanation, search, scoring, spaced repetition, and learner modeling support these capabilities.

## Benchmark and baseline

### Capability benchmark: HKU DeepTutor

[DeepTutor](https://github.com/HKUDS/DeepTutor) is the capability benchmark because its public design connects source grounding, evolving learner memory, personalized question generation, and a feedback loop.

GitLearnOS asks:

```text
What is the smallest portable control layer that preserves these learning-critical capabilities
while allowing learning to happen outside the AI runtime?
```

It does not reproduce DeepTutor's full application, multi-agent orchestration, RAG engines, database, provider layer, or product surfaces.

### Practical baseline: the original zhongkao repository

The original learning repository remains the implementation baseline for file discipline, review habits, mistake-to-model workflows, and real daily use.

```text
DeepTutor → capability direction
original zhongkao system → practical discipline
GitLearnOS → learner-owned, cross-channel, portable control layer
```

## Lightweight mapping

| Learning need | GitLearnOS implementation |
|---|---|
| cross-channel capture | inbox, source records, activity records |
| shared context | one target repository plus one active main agent |
| learner control | learning-policy, Markdown, Git history, undo |
| organization | organize skill, canonical state ownership, dashboard |
| personalized questions | question skill, reviews, handoff packs |
| external teacher coordination | gap lifecycle, handoffs, feedback reconciliation |
| mastery evidence | learner results, support level, delayed and transfer checks |
| automation | immediate and on-handoff rules; optional real scheduler |
| extensibility | portable router and focused SKILL.md files |

## Why GitHub

GitHub provides stable paths, explicit ownership, version history, inspectable evidence, portability across AI runtimes, and recovery from agent mistakes.

The repository is passive state plus declarative policy. The active agent performs organization, question generation, tutoring when requested, and writeback. Scheduled background behavior is optional and runtime-dependent.

## Why one main agent

Modern tool-capable runtimes such as ChatGPT Work can read connected state, reason across files, act, and verify within one workspace. GitLearnOS uses that as the standard: one capable main agent loads only the relevant skill.

Mandatory multi-agent orchestration would add handoff cost and reduce user control without being necessary for the lightweight product.

## Appropriate users

GitLearnOS fits a learner who:

- already learns across more than one channel;
- wants AI to reduce organization and review overhead;
- wants questions based on personal state rather than generic worksheets;
- values readable, portable, self-owned records;
- does not want to deploy another platform.

## Product boundary

Minimum:

```text
one capable main agent
+ one private target repository
+ GitLearnOS rules
+ one learning goal or input
```

Optional connected files, web research, code execution, visualization, native memory, and real schedulers may improve execution. None is required for the basic control layer.

## Promise

Success is not repository size, number of generated documents, or time spent talking to AI. Success means the learner can report an event once, receive useful organization or questions, and trust that the resulting state is correctly updated, visible, portable, and reversible.
