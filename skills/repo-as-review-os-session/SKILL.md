---
name: repo-as-review-os-session
description: Run an evidence-based GitLearnOS learning session. Use when the learner wants to learn, continue, practise, understand, be quizzed, or decide what to study now; diagnose an observable gap, adapt support, verify learning, and write back durable state.
---

# GitLearnOS Learning Session

## Purpose

Turn repository state into an actual learning interaction. This skill is the lightweight tutoring kernel; its outcome is improved or better-measured learning, not merely organized files.

## Minimum inputs

Read:

1. `dashboard.md`;
2. one active goal;
3. relevant parts of `learner-profile.md`;
4. due review or active knowledge gap;
5. only the source/model needed for this session.

If no due item exists, choose the smallest goal-critical item. If the source is unavailable, ask for the minimum excerpt or use a clearly labeled general-knowledge task.

## Session loop

### 1. Set one observable objective

Good:

```text
Independently recognize when triangle similarity is applicable and justify the correspondence.
```

Weak:

```text
Understand geometry better.
```

### 2. Elicit before teaching

Ask for recall, prediction, explanation, solution, comparison, or application before giving the complete answer. Record whether the response was independent, hinted, copied, or unavailable.

When the user explicitly requests a direct explanation, give it—but finish with a fresh check before making any mastery claim.

### 3. Diagnose one gap

Choose the best-supported diagnosis:

- prerequisite;
- recognition;
- method;
- execution;
- explanation;
- transfer;
- uncertain.

Do not turn every small slip into a permanent knowledge-gap file.

### 4. Adapt support

Use the least support that restores progress:

```text
cue
→ focused question
→ partial example
→ worked step
→ full explanation
```

Skip levels when needed. The goal is effective learning, not ritualized questioning.

### 5. Verify with a fresh task

Do not score the learner on repeating the exact demonstration. Use a changed number, context, representation, or comparison. Require transfer only when the goal requires application.

### 6. Score observable evidence

| Score | Result | Next review |
|---|---|---|
| 0 | still incorrect after substantial support | 1 day |
| 1 | correct with major hints or imitation | 2 days |
| 2 | correct with a minor hint or small execution error | 4 days |
| 3 | independently correct; transfer succeeds when required | 7 days |

After two consecutive score-3 reviews, double the prior interval up to 30 days.

### 7. Write back selectively

Update only what changed:

- `reviews/`: prompt, response summary, hint level, score, next review;
- `knowledge-gaps/`: new or materially changed diagnosis and evidence;
- `models/`: reusable cue/method refined by the session;
- `learner-profile.md`: repeated or durable pattern with evidence link;
- `dashboard.md`: due work and next action;
- `sessions/`: concise log only when the session materially changed state.

Do not store hidden reasoning or full private conversation transcripts. Store observable evidence and a short outcome summary.

## Stop conditions

Stop or narrow the session when:

- the learner is fatigued;
- the source needed for correctness is unavailable;
- the goal changed;
- the task is too large for one observable objective;
- further questioning no longer adds learning value.

## Output

```text
Session objective:
Evidence score: 0 / 1 / 2 / 3 / not assessed
Observed evidence:
Support used:
Files updated:
Next review or action:
```
