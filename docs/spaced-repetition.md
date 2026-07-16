# Evidence-Based Spaced Repetition

GitLearnOS schedules review from observed performance, not from file creation or the learner merely seeing an explanation.

Use this protocol for knowledge or skills that should be retrieved or performed again after time. Do not force open research, exploratory reading, creative work, or project milestones into 0–3 spaced repetition; use the goal's rubric, tests, artifact, or milestone evidence instead.

## Evidence score

Use one score after a fresh check:

| Score | Observable result | Default interval |
|---|---|---|
| 0 | no correct recall after substantial support | 1 day |
| 1 | correct only with major hints or imitation | 2 days |
| 2 | correct with a minor hint or small execution error | 4 days |
| 3 | independently correct; transfer succeeds when required | 7 days |

After two consecutive score-3 reviews, double the prior interval up to 30 days. A later lower score resets the schedule from that new score.

## What counts as evidence

Strong evidence:

- independent delayed recall;
- correct explanation in the learner's own words;
- solving a changed example;
- successful transfer to a new context;
- detecting and correcting one's own error.

Weak or non-mastery evidence:

- reading the answer;
- copying a worked example;
- immediate repetition;
- completing a file or worksheet;
- saying “I understand” without a check.

Record weak evidence honestly. It can guide support, but it cannot justify score 3 or `stable`.

## Review record

Every scored review should include:

```text
reviewed item:
date:
prompt or task:
learner response summary:
hint level: none / minor / major / full explanation
correctness:
transfer required: yes / no
transfer result:
score: 0 / 1 / 2 / 3
previous interval:
next review:
evidence link:
```

## Item state

Keep status simple:

- `new`: not yet assessed;
- `learning`: evidence score 0–2 or only immediate evidence;
- `stable`: at least two successful reviews including delayed independent evidence;
- `reopened`: previously stable but later failed;
- `blocked`: missing source or prerequisite prevents a valid check.

`goal-critical` is a priority flag, not a memory state.

## Selection rule

Choose review work in this order:

1. overdue goal-critical items;
2. recent score 0 or 1;
3. due active knowledge gaps;
4. score-2 items needing transfer;
5. stable items whose interval has elapsed.

Keep a session small enough to finish and score. A generated but unattempted review stays `planned`.

## Date rule

Use explicit ISO dates (`YYYY-MM-DD`) and record the score that produced the date. If the runtime cannot calculate or write the date, report it as pending instead of guessing that an automation will handle it.

## Principle

For retained knowledge and repeatable skills, one success is not stable mastery. Stability requires later retrieval or performance. Other learning needs use their declared evidence contract.
