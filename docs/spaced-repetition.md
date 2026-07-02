# Spaced Repetition Model

Repo as Review OS should include spaced repetition.

The goal is simple: important knowledge should return before it is forgotten.

## Why it matters

A learning system should not only store what the user once learned. It should bring old material back at the right time.

This prevents the common failure where a user once understood a problem, but forgets it months later.

## Review schedule

A simple default schedule:

```text
first learn
→ same day
→ next day
→ 3 days later
→ 7 days later
→ 14 days later
→ 30 days later
→ before the goal deadline
```

The schedule can be changed for each user.

## What gets scheduled

The AI should schedule review for:

- mistake models;
- important problem cards;
- weak topics;
- vocabulary;
- writing material;
- formulas;
- recurring traps;
- goal-critical knowledge.

## Repository fields

Every reviewable item can include:

```text
First learned:
Last reviewed:
Next review:
Review count:
Memory status:
Goal link:
```

## Memory status

Recommended values:

- `new`
- `learning`
- `unstable`
- `stable`
- `forgotten`
- `goal-critical`

## AI behavior

When the AI sees a reviewable item, it should decide:

1. Is this tied to a goal?
2. When was it last reviewed?
3. Is it stable or forgotten?
4. Should it appear in the next practice set?
5. Should the next review date be updated?

## Automation

The practice generator should use spaced repetition.

It should not only pick recent items. It should also revive older items whose next review date has arrived.

## Practical rule

A problem is not finished when it is solved once.

It is finished only when the user can still recognize and solve its model after time has passed.
