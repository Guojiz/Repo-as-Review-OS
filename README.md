# GitLearnOS

![GitLearnOS overview](docs/assets/repo-as-review-os-map.svg)

[中文](README.zh-CN.md) · [Website](https://gitlearnos.jizheng.chatgpt.site)

**GitLearnOS is a learner-owned control layer: organize automatically, generate targeted questions, and keep durable state in sync.**

Learning can happen with a teacher, in class, on paper, in a textbook or practice platform, with another AI, or in ChatGPT Work. GitLearnOS does not pull all learning into one platform. One replaceable main agent coordinates the resulting material, questions, feedback, evidence, and next actions in the learner's own GitHub repository.

The repository retains the historical name `Repo-as-Review-OS`; the product concept is **GitLearnOS**. Status: early public release. See [PUBLIC-ALPHA.md](PUBLIC-ALPHA.md).

## Three core capabilities

| Capability | Required behavior |
|---|---|
| Automatic organization | Capture notes, mistakes, teacher feedback, and platform results; connect them to goals and gaps; deduplicate and surface the next action |
| Targeted question generation | Create diagnostic, variation, transfer, and review tasks—or a focused question pack for a teacher—from sources and learner state |
| Automated execution and writeback | Apply safe state changes, schedule follow-up, retire obsolete tasks, and return an inspectable, reversible receipt |

Explanation, search, and live AI tutoring are useful supporting capabilities, not prerequisites. A learner may work mainly with a human teacher and use GitLearnOS only to organize, generate questions, and maintain continuity.

## One repository, subject folders

The learner authorizes one GitHub repository. Shared policy and cross-subject planning stay at the root; each subject keeps its own working state under `subjects/<subject>/`.

```text
my-gitlearnos/
├── AGENTS.md
├── learning-policy.md
├── dashboard.md
├── learner-profile.md
└── subjects/
    ├── math/
    ├── english/
    └── coding/
```

The agent infers the subject from the current material, routes all subject-specific files into that folder, and asks only when ambiguity would cause a wrong write. A natural-language correction such as “this belongs to physics” overrides routing. It never creates empty folder trees just to look complete.

See [Subject Folder Model](docs/subject-folder-model.md).

## Support school and self-study together

GitLearnOS shares knowledge state while preserving two goal tracks:

| Track | Typical work | Agent focus |
|---|---|---|
| school | curriculum, homework, exams, class notes, teacher requirements and feedback | align with school methods and deadlines, prepare help, organize mistakes, generate current-course questions |
| self-study | interests, prerequisite repair, advanced learning, reading, projects, personal challenges | preserve continuity, plan paths, generate open and transfer tasks, prevent short-term school work from consuming everything |

One concept keeps one model and mastery history but may serve several goals. The dashboard marks each task's track, and `learning-policy.md` can express rules such as school-first during exam weeks while preserving self-study time otherwise.

## Adapt to diverse learning needs

School and self-study are contexts, not product limits. The same organization, question, and automation engines adapt by need:

| Need | Organization focus | Question or output focus |
|---|---|---|
| current course and homework | scope, teacher constraints, deadlines, class feedback | current method, assignment form, teacher handoff |
| remediation | prerequisites, error chains, recurring blockers | small diagnostics and targeted variations |
| exam preparation | syllabus, mistake distribution, time pressure | timed tasks, mixed retrieval, scoring, scheduling |
| advanced or interest study | concept map, source path, open questions | explanation, comparison, exploration, broad transfer |
| project or skill | milestones, artifacts, feedback, real constraints | implementation tasks, tests, artifact rubric, retrospective |
| reading or research | sources, claims, evidence, uncertainty | extraction, critique, synthesis, research questions |

The agent first infers or confirms the current need, then adapts question form, evidence contract, and automation intensity. Not all learning requires a 0–3 problem score: code tests, artifacts, oral performance, critical reading, and teacher feedback may be the right evidence.

## Start in two minutes

You need one main agent that can read this template and operate a private target repository, plus one learning goal.

Send this:

```text
Use https://github.com/Guojiz/Repo-as-Review-OS as the GitLearnOS template.
My private learning repository is: <target repository>
The subject for this first input is: <subject>
My learning goal is: <goal>

Read START-HERE.md and AGENTS.md first. Use
skills/repo-as-review-os/SKILL.md when skills are supported. Detect actual
permissions, preserve existing files, and use safe-auto: perform safe,
reversible organization, question generation, state sync, and writeback;
ask only for high-impact actions. Do not force the request into an AI
tutoring session. Never write my personal state into the template repository.
Keep shared policy at the repository root and route subject-specific state to
subjects/<subject>/. Create only files needed by the current learning event.
Finish with a concise receipt of changes, evidence, and the next action.
```

ChatGPT Work is one primary path: when the target repository is connected, the agent should inspect and perform safe work directly. A read-only chat can produce exact pending writeback, but must not claim the repository changed.

## Learn anywhere

Typical requests:

- “Organize these two pages of class notes and give me three variations.”
- “Finish school priorities by Thursday but preserve two hours for my coding self-study.”
- “Prepare my recent geometry gaps as a question pack for tomorrow's tutor.”
- “My teacher resolved the second issue: check corresponding angles first. Here are my notes.”
- “Import today's practice-platform mistakes and test me again this weekend.”
- “Record this only; do not schedule a review.”
- “Undo the last learning update.”

The learner should not have to name folders or templates. The agent identifies the intent, chooses the smallest durable state change, acts, and reports.

## Two loops

The primary loop coordinates learning across channels:

```text
capture any learning event
→ connect goal, source, and gap
→ route to teacher, learner, AI, or another channel
→ organize feedback or generate questions
→ write back automatically
→ update the next action
```

When live AI tutoring is useful, use the optional teaching loop:

```text
learner attempt
→ diagnosis
→ minimum useful support
→ fresh verification
→ evidence score
→ writeback and review
```

“Resolved by a teacher” and “independently mastered” are different states. GitLearnOS can accept an external resolution and stop redundant teaching while recording whether mastery has been verified.

## Question generation is not random worksheet generation

Each question set should state:

- the goal and gap it serves;
- the sources, models, and prior evidence used;
- whether it is diagnostic, practice, variation, transfer, or delayed review;
- difficulty, time budget, answer key or rubric;
- learner result, support used, and next action.

A teacher-facing question pack is also a first-class output. It should contain the problem locator, learner attempt, exact blocker, and what the teacher should check.

## Automation with learner control

The recommended default is `safe-auto`:

| Mode | Behavior |
|---|---|
| `safe-auto` | perform safe, low-risk, reversible actions and report afterward |
| `preview` | show the planned changes before writing |
| `manual` | provide suggestions or pending writeback only |

The target repository's `learning-policy.md` stores rules such as raw-conversation retention, automatic verification, and whether teacher names may be recorded. Natural language can override a single event: “do not store this,” “organize only,” or “always link teacher feedback.”

Automation has three tiers:

1. **Immediate:** organize, generate, and write back after user input;
2. **On handoff:** inspect due work, unprocessed inbox items, and waiting feedback whenever an agent resumes;
3. **Background:** schedule only when the current runtime truly supports it; never require it for the portable base.

Rules and state stay in the repository while the executing agent may change. Automation must be transparent and idempotent, and one learning event should become one reversible update when the runtime supports atomic writes.

## What it is

```text
any learning channel
+ one replaceable main AI agent
+ one learner-owned repository with subject folders
+ GitLearnOS rules and skills
= a portable personal learning control layer
```

GitLearnOS is not:

- a replacement for an AI application or human teacher;
- a required multi-agent framework;
- a RAG service or vector database;
- a drive for every textbook and private original;
- a note system that creates files for its own sake.

## Design standard

GitLearnOS is evaluated by whether it preserves the learning-critical loop with the smallest practical system:

1. outputs remain grounded in accessible sources;
2. learner state evolves from evidence rather than claims;
3. current gaps drive targeted questions;
4. teacher feedback and learner results change future actions;
5. every automation is inspectable, reversible, and controlled by the learner.

It does not reproduce a full runtime, frontend, RAG stack, multi-agent system, database, or knowledge platform. The original `zhongkao` learning repository remains the practical implementation baseline.

See [Product Positioning](docs/product-positioning.md) and [Evaluation Standard](docs/agentic-tutoring-standard.md).

## Minimal target repository

```text
my-gitlearnos/
├── AGENTS.md
├── learning-policy.md
├── dashboard.md
├── learner-profile.md
├── subjects/
│   └── math/
│       ├── goals/
│       ├── sources/
│       ├── knowledge-gaps/
│       └── reviews/
└── archive/
```

Git does not preserve empty folders. Create only the active subject and the state needed now; optional folders such as `handoffs/`, `models/`, or `sessions/` appear on first use.

## Skills

Start at [skills/repo-as-review-os/SKILL.md](skills/repo-as-review-os/SKILL.md). Load progressively by intent:

- setup: bootstrap or migrate;
- organize: capture, deduplicate, connect, and reconcile external feedback;
- question: personalized practice and external question packs;
- session: optional live AI tutoring;
- source / model: provenance and reusable understanding;
- review: scoring, scheduling, and result writeback;
- maintenance: consistency, safe repair, and handoff health.

One main agent is the standard runtime. These responsibilities do not require separate agents.

## Sources, privacy, and memory

- Keep real state in a private target repository by default.
- Keep copyrighted books, teacher originals, private screenshots, and large originals local or in authorized sources.
- Store only necessary summaries, locators, and derived state on GitHub.
- Do not retain full conversations by default.
- The learner can inspect, edit, export, switch agents, or undo updates.
- When native AI memory conflicts with the repository, inspect evidence and honor the learner's correction.

## Examples and entry points

- [Chinese mathematics demo](examples/zh-CN/demo-zhongkao-lite/)
- [Quickstart](QUICKSTART.md)
- [Agent entry](START-HERE.md)
- [Canonical agent rules](AGENTS.md)
- [Runtime adaptation](docs/runtime-self-adaptation.md)
- [Templates](templates/)

## License

Apache License 2.0. See [LICENSE](LICENSE).
