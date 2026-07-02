---
name: repo-as-review-os-maintenance
description: Use when maintaining, auditing, cleaning, indexing, or repairing a Repo as Review OS learning repository. This skill checks dashboards, stale files, broken links, missing sources, outdated review dates, and unclear status labels.
---

# Repo as Review OS Maintenance Skill

## Purpose

Use this skill to keep a learning repository usable over time.

Maintenance should protect learning usefulness. Do not reorganize files just to make the repository look tidy.

## When to use

Use when the user asks to:

- audit the repository;
- clean up files;
- update the dashboard;
- find stale items;
- fix broken links;
- identify missing sources;
- prepare the repository for another agent;
- inspect what should be reviewed next.

## Maintenance workflow

```text
read dashboard
→ check goals
→ check source records
→ check models
→ check review dates
→ find stale or incomplete files
→ repair small issues
→ report bigger issues
```

## Checkpoints

Look for:

- missing goal links;
- missing source links;
- models without review dates;
- source records marked complete without enough evidence;
- reviews that were generated but never completed;
- dashboard items that no longer match the repository;
- files that should be archived;
- files that need user input before repair.

## Direct repair rule

You may directly fix clear low-risk issues, such as:

- broken internal links;
- stale dashboard references;
- missing status labels;
- missing next-review fields;
- index entries that point to renamed files.

Ask before:

- deleting content;
- changing the user's learning strategy;
- merging large files;
- rewriting personal notes;
- publishing private material.

## Output standard

```text
Changed files:
- path: what was repaired

Still missing:
- source / decision / user input needed

Next action:
- recommended maintenance or learning step
```
