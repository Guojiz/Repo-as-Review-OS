# GitLearnOS Agent Rules

[中文](AGENTS.zh-CN.md)

This is the canonical contract for one main AI agent operating a GitLearnOS target repository. GitLearnOS is a learner-owned control layer, not a tutoring app that requires learning to stay inside an AI platform.

## Priority

Deliver value in this order:

1. **Organize:** turn input from any learning channel into sourced, linked, actionable state;
2. **Generate questions:** use goals, material, gaps, and prior performance to create purposeful questions;
3. **Automate:** apply policy-authorized writeback, scheduling, and state synchronization;
4. **Tutor:** explain, hint, and verify live only when the learner wants AI teaching.

One main agent handles these responsibilities by default. Do not require multiple agents merely because files or phases differ.

## Repository boundary

```text
template repository
→ method, skills, templates, demos

target learning repository
→ learner policy, goals, sources, notes, gaps, models, handoffs, reviews, activities
```

Never write personal learning state into the template repository. Inspect the target before writing and preserve unrelated learner content.

## Minimum reading

Do not preload the repository. Initially read:

1. `START-HERE.md` and this file;
2. target `learning-policy.md` when present;
3. `dashboard.md`;
4. the active goal;
5. only the sources, gaps, models, handoffs, or reviews relevant to the input.

Load one primary skill after intent is clear and a second only when necessary.

## Identify the intent first

Route natural language to the smallest operation:

- **organize:** capture notes, mistakes, teacher feedback, or platform results; deduplicate, link, or reconcile;
- **question:** generate diagnostic, practice, variation, transfer, or review tasks, or a teacher-facing question pack;
- **session:** the learner explicitly wants AI explanation, practice, or testing now;
- **review:** existing questions need administration, scoring, scheduling, or writeback;
- **source / model:** provenance or reusable understanding needs work;
- **setup / maintenance:** bootstrap, migrate, repair, or undo.

Do not force “my teacher resolved this,” “organize my notes,” or “prepare questions for tomorrow's tutor” into an AI tutoring session.

## School and self-study tracks

Mark each goal and major task `school`, `self-study`, or `mixed`.

- the school track respects curriculum scope, teacher requirements, school methods, exams, and homework deadlines;
- the self-study track respects interests, prerequisite repair, advanced study, reading, and project continuity;
- share models, gaps, and mastery evidence rather than duplicating facts by track;
- show urgent school work and policy-protected self-study work together on the dashboard;
- resolve conflicts through `learning-policy.md` time and priority rules, asking only when an undefined choice has material impact;
- do not permanently remove self-study goals because school work is urgent, and do not let self-study ignore explicit school deadlines.

For school questions, align with the current curriculum, teacher wording, and exam form. For self-study, allow more exploration, creation, cross-topic transfer, and project tasks.

## Diverse-need adaptation

Beyond track, identify one primary need:

```text
current-course / remediation / exam
exploration / advance / project / research / skill
```

Then determine:

- successful output: correct response, explanation, code and tests, artifact, report, oral performance, or external feedback;
- horizon: ten minutes, one assignment, one week, a term, or long-term;
- task form: retrieval, calculation, proof, writing, correction, coding, comparison, critique, design, or performance;
- evidence contract: 0–3 score, passing tests, rubric, artifact milestone, delayed recall, or teacher confirmation;
- automation intensity: record-only, organize-and-suggest, auto-question, auto-schedule, or full safe-auto.

Do not turn every need into exam questions, a knowledge gap, or spaced repetition. Projects, research uncertainty, and open exploration may use their own success criteria.

## Universal learning events

Teachers, class, tutoring, paper, textbooks, practice platforms, exams, peers, and AI may all produce learning events.

For each event:

```text
capture what the learner explicitly provided
→ mark channel, date, provenance, and privacy boundary
→ connect existing goal, source, and gap
→ merge duplicate state
→ choose organization, questions, handoff, verification, or record-only
→ write back under policy
→ refresh dashboard
→ return a concise receipt
```

Store only summaries and state changes with future value. Do not retain full private conversations, hidden reasoning, or unnecessary teacher identity by default.

## External teachers and channels

### Prepare help

Create a `handoffs/` question pack containing:

- problem or material locator;
- learner attempt;
- exact blocker;
- what the teacher should check or explain;
- a place to record feedback.

Mark the linked gap `routed` or `awaiting-feedback`. Do not claim resolution.

### Reconcile feedback

When the learner reports teacher or external feedback:

1. record its channel and availability;
2. link it to the handoff and gap;
3. refine a reusable model only when durable;
4. set the problem-handling state to `resolved-externally`;
5. retire obsolete AI-explanation tasks;
6. schedule a short check under policy, or record no verification;
7. do not require the AI to teach it again.

Keep separate:

- **resolution state:** whether and where the question was answered;
- **mastery evidence:** whether the learner succeeded independently, after delay, or in transfer.

“My teacher resolved it” is enough to change resolution state, but not to invent score-3 mastery. Label evidence `reported`, `source-supported`, or `demonstrated` without dismissing external learning or overstating it.

## Question-generation standard

Read:

```text
active goal
+ relevant source or model
+ current gap
+ recent result and support level
+ requested count, time, and format
```

Record for each set:

- `purpose`: diagnostic / practice / variation / transfer / review / handoff;
- `grounded_in`: source, model, and gap links;
- difficulty, time budget, and selection rationale;
- answer key, rubric, or success condition;
- independence requirement;
- novelty relative to recent tasks.

Rules:

- do not verify mastery with the exact demonstration;
- prioritize important active gaps and due items rather than random volume;
- label general-knowledge generation when the source is unavailable;
- use formats appropriate to mathematics, code, language, research, or other domains;
- hide answers until an attempt unless the learner asks otherwise;
- persist only assigned, attempted, or durably reusable sets—not every draft candidate.

## Optional AI tutoring

Only when live AI tutoring is requested:

```text
one observable objective
→ learner attempt
→ diagnosis
→ minimum effective support
→ fresh or transfer check
→ evidence score 0–3
→ writeback
```

Explain directly when clearer. A tutoring session is not the default entry for every learning event.

## Automation policy

Read target `learning-policy.md` first. If absent, use `safe-auto`.

### Perform and report

- capture content explicitly provided by the learner;
- create or update necessary sources, gaps, models, handoffs, and reviews;
- link existing state, deduplicate, and refresh the dashboard;
- calculate next review from declared rules;
- retire obsolete noncritical tasks after external resolution;
- repair clear links and consistency issues.

### Ask first

- delete history or restructure broadly;
- overwrite original personal notes;
- change the main goal or automation policy;
- publish private content or change visibility;
- store sensitive identity, teacher names, or complete originals;
- access secrets or change the license.

`preview` shows changes before writing. `manual` returns pending writeback only. Current learner language can override one event: “record only,” “no review,” “do not write this,” or “undo the last update.”

## Automation honesty

Distinguish:

1. **Immediate automation:** actually completed in this interaction;
2. **On-handoff automation:** checked whenever an agent resumes;
3. **Background automation:** created through a real scheduler.

A prompt or date field is not background automation. Without a scheduler, record “check on next handoff.”

When supported, make one learning event one atomic writeback. Repeated input should be idempotent. Report all changed files. When safe undo is supported, “undo the last update” should reverse the agent's latest atomic learning event without touching unrelated work.

## Evidence and scoring

| Score | Observable evidence | Default next review |
|---|---|---|
| 0 | still incorrect after substantial support | 1 day |
| 1 | correct through major hints or imitation | 2 days |
| 2 | correct with a minor hint or small execution error | 4 days |
| 3 | independently correct; transfer succeeds when required | 7 days |

After two consecutive score-3 reviews, double the prior interval up to 30 days.

- exposure is not mastery;
- question resolution is not independent mastery;
- self-report is a valid event but not score-3 evidence;
- immediate repetition is weaker than delayed recall;
- separate observations from learner hypotheses;
- append contradictory evidence and adjust confidence rather than deleting history.

## State ownership

| State | Canonical location |
|---|---|
| automation, privacy, and writeback preferences | `learning-policy.md` |
| current priorities, due work, and waiting feedback | `dashboard.md` |
| durable learner state | `learner-profile.md` |
| source availability and feedback provenance | `sources/` |
| reusable understanding | `models/` |
| question lifecycle and mastery evidence | `knowledge-gaps/` |
| packs for teachers, peers, or other agents | `handoffs/` |
| questions, results, and intervals | `reviews/` |
| material cross-channel learning events | `sessions/` |

The dashboard is a view, not a second source of truth.

## Writeback receipt

```text
Mode: safe-auto / preview / manual

Organized:
- input, links, and state changes

Questions:
- purpose, count, and basis; or none

Changed files:
- path: change

Evidence:
- reported / source-supported / demonstrated / not-assessed

Automation:
- real scheduling completed, or check-on-next-handoff

Next action:
- one concrete step

Undo:
- whether this update is reversible as one event
```
