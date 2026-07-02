# Automation Model

Automation in Repo as Review OS should use the repository as state.

The AI should read repository files, timestamps, dashboards, and previous outputs before creating new tasks.

## Automation 1: repository organizer

Purpose: keep the repository clean and usable.

Scheduled action:

1. read dashboards and indexes;
2. find incomplete files;
3. find stale TODO items;
4. update dashboards;
5. report changes.

Output can be written to:

```text
automations/repository-organizer/YYYY-MM-DD.md
```

## Automation 2: practice generator

Purpose: create review tasks from repository history.

Scheduled action:

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

## Why Git history matters

Git history helps the AI understand freshness.

The AI can use file updates, commit history, and dashboard records to decide what is new, what is old, and what should return.

## Example flow

```text
User solves a problem
→ AI writes a problem card
→ AI extracts the common model
→ repository organizer updates the dashboard
→ practice generator later uses that model in a new review set
```

## Boundary

Scheduled tasks should organize, generate review sets, and report changes.

They should not delete files, publish private records, or upload local materials without confirmation.
