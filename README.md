# GitLearnOS

![GitLearnOS overview](docs/assets/repo-as-review-os-map.svg)

[中文说明](README.zh-CN.md)

**A lightweight, GitHub-native tutoring toolkit for existing AI agents.**

GitLearnOS turns one target repository into an inspectable learning state: goals, sources, learner profile, knowledge gaps, models, review evidence, and next actions. It is a toolkit of rules, skills, and Markdown templates—not a standalone tutoring platform.

The repository keeps the historical name `Repo-as-Review-OS`; the product concept is **GitLearnOS**. Current status: public alpha. See [PUBLIC-ALPHA.md](PUBLIC-ALPHA.md).

## Two-minute start

You need one capable AI agent, one private target repository, and one learning goal.

Send this to an agent that can read this template and write to your target repository:

```text
Read https://github.com/Guojiz/Repo-as-Review-OS as the GitLearnOS template.
My personal learning repository is: <target repository URL>
My first learning goal is: <goal>

Do not read the whole template before acting. Start with START-HERE.md and AGENTS.md. If skills are supported, use skills/repo-as-review-os/SKILL.md. Detect your actual permissions, inspect the target repository, preserve existing files, create only the minimal missing learning state, and then run the first evidence-based learning session. Never write my personal learning data into the template repository. Report every changed file.
```

In a tool-capable workspace such as ChatGPT Work, the agent should inspect and edit the connected target repository directly. Copy-and-paste setup is only a fallback for read-only chat environments.

## What it is

```text
one main AI agent
+ one target GitHub repository
+ one learning goal
+ GitLearnOS rules and skills
= a portable learning loop
```

The target repository stores durable learning state. The active AI runtime explains, questions, searches, creates practice, and writes back only learning changes supported by evidence.

GitLearnOS is not:

- a replacement for the AI app;
- a required multi-agent framework;
- a RAG server or vector database;
- a place to upload every textbook or private file;
- a note archive that grows without a learning goal.

## Learning loop

```text
goal
→ grounded source
→ learner attempt
→ diagnosed knowledge gap
→ explanation or hint
→ transfer check
→ evidence score
→ model/profile/review update
→ next action
```

The key rule is simple: **exposure is not mastery**. An item is not marked stable because the AI explained it or because the learner said “I understand.” Stable progress requires observed recall and, when appropriate, a transfer check.

## Benchmark: DeepTutor, compressed into a toolkit

[HKU DeepTutor](https://github.com/HKUDS/DeepTutor) is the capability benchmark. GitLearnOS does not attempt to reproduce DeepTutor's full runtime, UI, multi-agent system, RAG engines, Partners, or knowledge platform.

Instead, it keeps a lightweight equivalent of the learning-critical parts:

| DeepTutor direction | GitLearnOS lightweight equivalent |
|---|---|
| shared personalization substrate | one target repository plus `learner-profile.md` |
| source-grounded learning | `sources/` with honest availability and evidence fields |
| evolving learner memory | evidence-linked profile and knowledge-gap files |
| closed tutoring loop | session skill, review evidence, and deterministic writeback |
| extensible skills | portable `SKILL.md` suite |
| inspectable state | Markdown and Git history |

The original `zhongkao` learning repository remains the practical implementation baseline: it shows which file discipline and review habits worked in real use. DeepTutor sets the capability direction; the original system tests whether the lightweight implementation remains useful.

See [Product Positioning](docs/product-positioning.md) and [Evaluation Standard](docs/agentic-tutoring-standard.md).

## Minimum target repository

```text
my-gitlearnos/
├── AGENTS.md
├── dashboard.md
├── learner-profile.md
├── goals/
├── inbox/
├── sources/
├── models/
├── knowledge-gaps/
├── reviews/
├── sessions/
├── templates/
└── archive/
```

Git does not track empty folders. A setup agent should create only the files and folders needed for the first goal, then add other folders when they become useful.

## Use the right entrance

- **Learner:** [30-Second Intro](docs/30-second-intro.md) → [Quickstart](QUICKSTART.md)
- **AI agent:** [START-HERE.md](START-HERE.md) → [AGENTS.md](AGENTS.md) → [skill router](skills/repo-as-review-os/SKILL.md) when supported
- **Designer or contributor:** [Product Positioning](docs/product-positioning.md) → [Evaluation Standard](docs/agentic-tutoring-standard.md)

The AI should not preload every document. It should read the two entry files, inspect the target learning state, and open deeper references only for the current task.

## Skills

The portable suite contains focused skills for:

- setup and migration;
- live learning sessions;
- source handling;
- reusable model extraction;
- review generation and scoring;
- repository maintenance.

Start with [skills/repo-as-review-os/SKILL.md](skills/repo-as-review-os/SKILL.md). The live-session skill is the tutoring kernel; it prevents the repository from becoming only a file organizer.

## Sources, privacy, and memory

- Keep real learning records in a private target repository.
- Keep copyrighted books, raw scans, private screenshots, and large original files local or in an authorized connected source.
- Store source records and the minimum useful excerpt or reference in GitHub.
- Treat `learner-profile.md` as the inspectable learner-state anchor.
- Use native AI memory only for stable preferences and durable patterns.
- If native memory conflicts with the target repository, verify the evidence and update the stale layer explicitly.

## Demos

- [Chinese exam-math demo](examples/zh-CN/demo-zhongkao-lite/)
- [English research-reading demo](examples/en/demo-research-reading-lite/)
- [English SAT demo](examples/en/demo-sat-lite/)

The demos are cleaned examples, not personal learning data.

## Important documents

- [QUICKSTART.md](QUICKSTART.md): shortest user setup path
- [START-HERE.md](START-HERE.md): short agent handoff
- [AGENTS.md](AGENTS.md): canonical execution and safety rules
- [docs/runtime-self-adaptation.md](docs/runtime-self-adaptation.md): capability-based runtime adaptation
- [docs/spaced-repetition.md](docs/spaced-repetition.md): evidence score and next-review rule
- [docs/product-positioning.md](docs/product-positioning.md): lightweight DeepTutor benchmark mapping
- [docs/agentic-tutoring-standard.md](docs/agentic-tutoring-standard.md): acceptance tests
- [templates/](templates/): target-repository state templates

## License

MIT License. See [LICENSE](LICENSE).
