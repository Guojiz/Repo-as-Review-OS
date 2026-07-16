# Quickstart

GitLearnOS works best with one main agent that can read the template and operate a private target repository. ChatGPT Work is one standard tool-capable path, but learning does not need to happen inside ChatGPT.

## Tool-capable path

1. Create or choose a private target repository.
2. Connect it to the current main agent.
3. Give one learning goal and the current input.
4. Let the agent organize, generate questions when useful, and write back.

```text
Use https://github.com/Guojiz/Repo-as-Review-OS as the GitLearnOS template.
Target repository: <link>
Learning goal: <goal>

Read START-HERE.md and AGENTS.md; use skills/repo-as-review-os/SKILL.md
when supported. Use safe-auto, preserve existing content, and directly perform
safe, reversible organization, question generation, synchronization, and
writeback. Do not default to an AI tutoring session. Report changes, evidence,
actual automation, and the next action.
```

Do not ask the learner to create folders, copy templates, or update the dashboard when the agent can do it.

## Minimum first state

```text
AGENTS.md
learning-policy.md
dashboard.md
learner-profile.md
goals/main-goal.md
```

Create `sources/`, `knowledge-gaps/`, `models/`, `handoffs/`, `reviews/`, or `sessions/` only on first real use.

## Everyday requests

```text
Organize these class notes, connect them to my recent gaps, and give me three variations.
```

```text
Prepare my unresolved items as a question pack for tomorrow's tutor.
```

```text
My teacher resolved the second item. Reconcile this feedback and my notes; do not reteach it.
```

```text
Import this practice-platform result, update my weak points, and test me this weekend.
```

```text
Record this only. Do not generate questions or schedule review.
```

```text
Undo the last learning update.
```

The learner describes the event and intent, not repository paths.

## Automation modes

- `safe-auto`: perform safe actions and report afterward; recommended;
- `preview`: show changes before writing;
- `manual`: return pending writeback only.

Immediate and on-handoff automation are core. Scheduled background reminders exist only when the current runtime provides a real scheduler.

## Read-only fallback

Without write access, the agent should:

1. read the minimum state supplied;
2. organize or generate questions;
3. return exact pending writeback;
4. state clearly that the repository has not changed.

## Success check

The agent can answer and act on:

- the active goal, due work, and waiting external feedback;
- where new input belongs;
- why these questions were generated instead of random ones;
- whether externally resolved issues stopped redundant teaching;
- every changed file;
- which automation actually ran;
- the next action and undo path.

If it only lists folders or makes the learner maintain files manually, setup is incomplete.

## Privacy

- Keep real state in a private target repository by default.
- Keep teacher originals, full copyrighted material, and private screenshots in authorized sources.
- Write back only necessary summaries, locators, and derived state.
- Do not retain full conversations or unnecessary identity by default.
