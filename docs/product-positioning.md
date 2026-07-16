# Product Positioning

GitLearnOS is a lightweight tutoring toolkit that attaches to an existing capable AI agent and uses a GitHub repository as durable, inspectable learning state.

It is not a standalone tutoring platform, a ChatGPT-only project, an Obsidian workflow, or a multi-agent framework.

## One sentence

```text
Use one capable AI agent to run an evidence-based learning loop over one learner-owned GitHub repository.
```

## Benchmark and baseline

GitLearnOS uses two different comparisons for two different questions.

### Capability benchmark: HKU DeepTutor

[DeepTutor](https://github.com/HKUDS/DeepTutor) is the capability benchmark because its published design connects source grounding, evolving learner memory, personalized question generation, and a closed tutoring loop in one shared runtime.

GitLearnOS asks:

```text
What is the smallest portable toolkit that preserves the learning-critical behavior
when a strong external AI runtime already exists?
```

It does not attempt to reproduce DeepTutor's:

- full application runtime or web interface;
- multi-agent orchestration and Partners;
- RAG engines, document parsers, or knowledge center;
- database, server, authentication, or model-provider layer;
- Co-Writer, Book, visualization, IM, or platform surfaces.

### Practical baseline: the original zhongkao repository

The original learning repository is the implementation baseline. It provides evidence about which file discipline, review habits, mistake-to-model workflow, and AI handoff patterns were useful in practice.

In short:

```text
DeepTutor → where tutoring capability should go
original zhongkao system → what proved useful in real repository practice
GitLearnOS → the portable, low-deployment-cost intersection
```

## Lightweight kernel

| Learning need | GitLearnOS implementation |
|---|---|
| shared context | one target repository plus one active agent session |
| source grounding | `sources/` with access and completeness states |
| learner personalization | `learner-profile.md` plus evidence-linked gaps |
| tutoring loop | attempt → diagnosis → support → transfer → score |
| practice generation | due gaps/models → focused review set |
| memory auditability | Markdown evidence links and Git history |
| extensibility | portable router and focused `SKILL.md` files |
| handoff | dashboard, canonical state files, and concise session evidence |

## Why GitHub

GitHub supplies what a chat transcript alone does not:

- stable file paths;
- explicit state ownership;
- writeback and version history;
- inspectable evidence;
- portability across AI runtimes;
- learner control over the data.

GitHub is passive state. The active AI runtime still has to read the relevant files, teach, observe the learner, and write back selectively.

## Why a toolkit instead of another app

A full platform is appropriate when a user wants a bundled UI, managed retrieval, built-in memory, background services, and a fixed runtime.

GitLearnOS is appropriate when the user already has a capable AI environment—such as ChatGPT Work or another tool-using agent—and wants:

- no separate server;
- no required database;
- no required API keys for the basic loop;
- one main agent rather than mandatory multi-agent orchestration;
- readable files and direct ownership;
- a method that survives switching AI products.

## Product boundary

Minimum runtime:

```text
one capable AI agent
+ one private target GitHub repository
+ GitLearnOS agent rules
+ one learning goal
```

Optional capabilities such as connected files, web research, code execution, visualization, native memory, automations, or local sources can improve the experience. The toolkit must remain useful without making those capabilities mandatory.

## Promise

GitLearnOS should make a learner's state easier to inspect, continue, and improve. Its success is measured by learning evidence and reliable handoff—not by repository size or the number of generated documents.
