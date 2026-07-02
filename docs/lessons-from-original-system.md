# Lessons from the Original System

The original learning repository shows that a Review OS must be more than a set of templates.

It needs operational rules that decide what the AI does before, during, and after each learning task.

## 1. Check before answering

Before answering, generating practice, or writing a card, the AI should check:

1. Is there a complete source?
2. Is there a similar mistake, model, or material card?
3. Is this output worth writing back to the repository?

## 2. Use status labels honestly

A file must not pretend to be more complete than it is.

Useful labels:

- `full-source`
- `draft-full`
- `index`
- `summary-only`
- `not-full-solution`
- `local-only-source`
- `needs-source`
- `todo`

## 3. Source first, then summary

If the source is missing, do not create a fake full card.

Create a queue item instead.

## 4. Lightweight first when time is short

Not every item needs a full card immediately.

When the user is in a sprint stage, the AI may create a lightweight note, label what is missing, and backfill later.

## 5. Directly fix obvious repository problems

If the AI has permission, it should fix obvious problems without asking every time:

- broken links;
- stale indexes;
- summary files marked as source;
- missing dashboard references;
- old status notes that mislead the next AI.

## 6. Ask before strategy changes

The AI should ask before:

- deleting major material;
- changing the user's learning strategy;
- publishing private material;
- replacing the expected method with a method outside the user's exam or training rules.

## 7. The repository serves the user

Do not optimize the repository for beauty alone.

The repository should help the user learn, remember, and act.

## Practical loop

```text
task arrives
→ check goal
→ check source
→ check similar models
→ answer or generate
→ write back if valuable
→ update index or dashboard
→ schedule review if needed
→ report changes and gaps
```
