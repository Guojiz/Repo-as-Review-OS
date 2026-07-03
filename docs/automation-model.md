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

## Repository organizer

Purpose: keep the repository clean and usable.

If running as a worker:

1. read dashboards and indexes;
2. find incomplete files;
3. find stale TODO items;
4. update dashboards;
5. report changes.

Output can be written to:

```text
automations/repository-organizer/YYYY-MM-DD.md
```

If running as prompt-only automation, output a handoff card instead.

## Practice generator

Purpose: create review tasks from repository history.

If running as a worker:

1. read recent problem cards;
2. read old weak points;
3. read active models;
4. check what has not appeared recently;
5. create a small review set;
6. write it back to the repository.

Output can be written to:

```text
automations/practice-generator/YYYY-MM-DD.md
```

If running as prompt-only automation, output a handoff card instead and wait for the user to continue in a tool-enabled chat.

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
