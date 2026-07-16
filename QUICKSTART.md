# Quickstart

GitLearnOS is easiest when the current AI workspace can read the template and write to one private target repository.

## Fast path: tool-capable workspace

Use this path for ChatGPT Work, a repository-aware coding agent, or another environment with connected GitHub write access.

1. Create or choose one private target repository.
2. Connect only that repository when possible.
3. Give the agent the target link and one learning goal.
4. Let the agent inspect, bootstrap, and run the first session.

Prompt:

```text
Use https://github.com/Guojiz/Repo-as-Review-OS as the GitLearnOS template.
Target repository: <URL>
Learning goal: <goal>

Read START-HERE.md and AGENTS.md first. Verify your actual permissions, inspect existing target files, preserve them, and create only the minimum missing state. If skills are supported, use skills/repo-as-review-os/SKILL.md. Then run one short learning session and write back only evidence-based changes. Report every changed file.
```

The agent should not ask you to manually recreate files it can safely create itself.

## Fallback: chat or read-only environment

If the AI cannot write to GitHub:

1. paste the active goal, dashboard, learner profile, and only the relevant source/model/gap excerpt;
2. complete one focused task;
3. ask the AI for a writeback block;
4. add that block to the target repository manually or in a later tool-capable session.

The AI must state that writeback is pending; it must not claim the repository was updated.

## Minimum first deployment

Do not copy the entire public template into a personal repository. Start with:

```text
AGENTS.md
dashboard.md
learner-profile.md
goals/main-goal.md
```

Then create the first relevant source, knowledge-gap, model, review, or session file. Add folders only when they contain real state; Git does not preserve empty directories.

## First useful commands

```text
Check my dashboard and run the most important 20-minute learning session.
```

```text
Record this material honestly, then test what I can recall before explaining it.
```

```text
Turn this mistake into a knowledge gap and reusable model, then schedule one transfer check.
```

```text
Score this review from observable evidence and update the next review date.
```

## Successful setup test

The agent should be able to answer, with file links:

- What is the active goal?
- What is due now?
- Which knowledge gaps have evidence?
- What did the learner actually demonstrate?
- What should happen next?
- Which files changed?

If it can only list folders but cannot run and record a learning session, setup is incomplete.

## Privacy

- Use a private target repository for real study records.
- Keep full copyrighted books, teacher files, raw screenshots, credentials, and sensitive personal material out of public GitHub.
- Use connected or local originals only when authorized, and write back the minimum durable learning state.

## Examples

- [Chinese exam-math demo](examples/zh-CN/demo-zhongkao-lite/)
- [English research-reading demo](examples/en/demo-research-reading-lite/)
- [English SAT demo](examples/en/demo-sat-lite/)
