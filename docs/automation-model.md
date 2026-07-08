# Automation Model

Automation in Repo as Review OS must be explicit about what the scheduled environment can actually do.

A scheduled reminder is not always a repository worker.

For the runtime capability map, see `docs/automation-runtime-matrix.md`.

## Two automation layers

```text
Prompt-only automation
→ produces a handoff card
→ reminds the user what to do next
→ does not claim repository work has already been done

Worker automation
→ has repository/tool access
→ reads repository state
→ writes outputs back to the repository
→ reports actual changes
```

## Important boundary

Some chat-app automations can run only as scheduled prompts.

In that case, the automation should be treated as a starter, not as the final worker.

It should not claim that the repository has been read, checked, repaired, updated, or exported unless the current run actually has the tools needed to do that work.

Use this rule:

```text
No tool access → handoff card only.
Tool access → real repository work may begin.
```

## Recommended minimal automation design

Do not overbuild many small automations.

For most learners, two routines are enough:

```text
1. Organizer + Critic + Revision
   → clean indexes, check weak points, critique stale or low-quality records, revise the repository state

2. Practice Generator
   → generate review or practice from weak points, old models, sources, and review schedule
```

The first routine maintains the learning system. The second routine creates new practice.

On ChatGPT mobile/app automation, keep these as simple scheduled starters or handoff cards unless the current chat actually has repository access.

On desktop or in a tool-enabled environment, the same routines may run with deeper file access and longer repository checks.

## ChatGPT-first workflow

A separate desktop agent is optional, not required.

For many users, the main workflow can be:

```text
ChatGPT app
→ ChatGPT memory for stable preferences and learner summary
→ GitHub repository for durable learning state
→ optional project space for fixed materials
```

ChatGPT memory and GitHub should stay aligned:

```text
GitHub = source of truth for files, indexes, review records, and history
ChatGPT memory = compact stable summary and preferences
```

When they conflict, trust GitHub first and update the memory summary or project instructions later.

A desktop agent, Codex, or local tool can be added only when the user wants more advanced automation, bulk file edits, local scripts, or a computer-based workflow. Do not present it as the default requirement.

## Visual and math work

Visual explanations do not require a separate agent by default.

If ChatGPT can create diagrams, images, code, tables, or interactive explanations in the current environment, use those built-in abilities first.

For math visualization, the AI may also produce a Desmos-ready expression list, a small HTML demo, or Python code when useful. Save only the useful artifact or link back into the repository when the current environment can write to GitHub.

## ChatGPT app vs desktop agents

```text
ChatGPT app / mobile automation
→ best for reminders, short handoff cards, user-triggered continuation, and memory/GitHub alignment checks
→ should not pretend it updated GitHub unless GitHub tools were actually used

Desktop agent / Codex / tool-enabled environment
→ optional enhanced mode
→ can run longer repository checks
→ can read many files
→ can write reports, practice sets, and dashboard updates
→ must still report every changed file
```

Multiple agents are optional. The repository is the shared state, so different tools can work on the same learning system if they can read and write the same GitHub repository.

## ChatGPT-style prompt-only automation

Use this mode when the scheduled automation may not have live repository tools.

The automation should output a short handoff card with:

1. Current position: this is only a handoff card / starter.
2. What the current chat or agent should continue doing.
3. Repository areas that should be checked first.
4. Risks to check, such as missing sources, stale dashboards, or old review items.
5. A user command to continue, such as: Continue repository check.

End with a clear warning:

```text
This automation itself does not mean the repository task has been completed. Continue in a tool-enabled chat or agent to execute it.
```

## Automation 1: Organizer + Critic + Revision

Purpose: keep the repository clean, accurate, and useful.

This combines three roles in one routine:

```text
Organizer
→ update indexes, dashboard links, stale TODOs, and review fields

Critic
→ find vague notes, weak source records, duplicated models, poor practice items, and unsupported summaries

Revision
→ make small safe fixes, queue uncertain fixes, and report what changed
```

If running as a worker:

1. read dashboard and indexes;
2. check goals, sources, models, reviews, automations, and any learner-state/profile file;
3. find incomplete files, stale TODO items, weak source records, duplicated models, and old review items;
4. update learner state or profile files if the repository uses them;
5. revise safe low-risk issues;
6. queue uncertain fixes instead of guessing;
7. update dashboard links and review fields;
8. report every changed file.

Output can be written to:

```text
automations/organizer-critic/YYYY-MM-DD.md
```

If running as prompt-only automation, output a handoff card instead.

Suggested prompt:

```text
Check my learning repository as Organizer + Critic + Revision.

First identify whether you have repository tools.

If you do not have repository tools, output only a handoff card: what to inspect first, what risks to check, and what command I should send next.

If you do have repository tools, read dashboard.md, goals/, sources/, models/, reviews/, automations/, and any learner-state/profile file. Update stale indexes, missing review fields, weak-point records, and dashboard links. Critique unclear notes, duplicated models, poor source records, and old practice items. Make small safe revisions, queue uncertain fixes, and report every file changed.
```

## Automation 2: Practice Generator

Purpose: create useful practice from repository history.

This routine should use the current repository state rather than inventing a generic quiz.

If running as a worker:

1. read recent review records;
2. read old weak points;
3. read active models;
4. read source records if needed;
5. check what has not appeared recently;
6. generate a small review set;
7. include answers and explanations;
8. link questions to weak points, models, or sources;
9. write the result back to the repository;
10. update review schedule or dashboard fields.

Output can be written to:

```text
automations/practice-generator/YYYY-MM-DD.md
```

If running as prompt-only automation, output a handoff card instead and wait for the user to continue in a tool-enabled chat.

Suggested prompt:

```text
Create a review/practice set from my learning repository.

First identify whether you have repository tools. If not, output only a handoff card.

If you have tools, read recent reviews, models, weak points, sources, and dashboard records. Generate a small practice set from active weak points and old material due for review. Include answers, explanations, linked source/model/review records, and suggested next review dates. Write the result back and report every changed file.
```

## Memory and GitHub sync check

Add this check to either routine when using ChatGPT:

```text
Compare the current ChatGPT memory/project instructions with the GitHub repository state. If memory contains a stable preference that is missing from the repository, suggest where it should be recorded. If GitHub contains a newer learner-state summary, suggest updating memory or project instructions. Do not silently overwrite either side.
```

## Handoff card pattern

Use this pattern for prompt-only automation:

```text
Title: Prepare repository handoff

This is only a scheduled starter and context handoff, not the actual repository worker.

Do not claim completed repository work before the current chat has actually used repository tools.

Output a concise handoff card with:
1. Current position.
2. Next task for the current chat.
3. Repository areas to inspect first.
4. Risks or missing sources to check.
5. User command to continue.
```

## Practice handoff pattern

```text
Title: Prepare practice handoff

This is only a scheduled starter and context handoff, not the actual practice generator.

Do not generate the final official review set before the current chat has actually read the repository.

Output a concise handoff card with:
1. Current position.
2. Forbidden claims before repository access.
3. User command to continue.
4. Repository areas to read first.
5. Generation rules after repository access.
```

## Optional worker implementation

A script or GitHub Actions worker may be added later, but it is not required for the protocol to work.

If added, it should start small:

```text
check required files
check required folders
write a simple health report
avoid rewriting learning content automatically
```

This kind of worker is a validation layer, not the whole learning agent.

## Why Git history matters

Git history helps the AI understand freshness.

The AI can use file updates, commit history, and dashboard records to decide what is new, what is old, and what should return.

But this only applies when the current environment can actually read Git history.

## Boundary

Scheduled tasks should never pretend to have used tools that were not available.

If the environment is prompt-only, the automation is only a starter.

If the environment has repository access, the automation may act as a worker.

Deleting files, publishing private records, or uploading local materials still requires confirmation.