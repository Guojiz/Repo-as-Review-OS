# Runtime Self-Adaptation

GitLearnOS specifies a learning protocol; the current AI environment supplies the tools.

## Detect capabilities, not brand names

Before acting, determine:

```text
Can I read the template repository?
Can I read and write the target repository?
Can I access the learner's authorized source files?
Can I load file-based skills or repository instructions?
Do I have native memory or project instructions?
Can I schedule a real automation, or only draft a prompt?
Which step genuinely requires the user?
```

Test safe capabilities through available tools. Product names alone do not prove access.

## Work-mode fast path

Use this path when the current workspace can inspect files, call connected apps or repository tools, and write to the target repository—for example, a properly connected ChatGPT Work session.

```text
verify target and permissions
→ inspect existing target state
→ read entry rules + active files only
→ perform the learning task directly
→ write back durable evidence
→ verify changed files
→ report the result
```

Do not ask the user to paste repository content, recreate files, or perform a connector action that the current authorized runtime can complete itself.

Connected files or apps can serve as active source surfaces. GitHub remains the durable structured learning state; do not dump every original into it.

## Repository-aware agent path

For Codex, Claude Code, Cursor, or another agent working in a local checkout:

- obey repository-level instructions;
- inspect the working tree before edits;
- preserve unrelated changes;
- use the same learning-session and evidence rules;
- keep local originals outside public GitHub;
- report verification and changed files.

These agents can run GitLearnOS directly when they are the user's chosen active agent; they are not limited to deploying another runtime.

## Native chat path

If the AI has memory or project context but no target write access:

- use the current chat as the active teaching surface;
- read connected sources only when actually available;
- produce a concise writeback block;
- mark repository updates as pending;
- keep stable preferences separate from fast-changing learner state.

## Single-context fallback

Request only:

- active goal;
- relevant learner-profile excerpt;
- one source/model/gap/review excerpt;
- the current task.

Complete one focused learning loop and return the exact state update for later writeback. Never pretend to have persistent memory or repository access.

## Automation honesty

Distinguish:

```text
real scheduled automation
→ created through an available scheduling system

prompt or plan
→ instructions only; nothing will run automatically
```

Record automation output only after it exists. The basic GitLearnOS loop must work without background automation.

## Permission boundary

Use ordinary target-repository writes required by the user's task when authorized. Ask before deletion, broad overwrite, visibility change, private publication, secrets, or license changes.

## Rule

Adapt the execution mechanism, not the learning standard. Every runtime should preserve source honesty, learner attempts, evidence-based scoring, selective writeback, and clear next action.
