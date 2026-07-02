# Agent Runtime Guide

This guide is for any AI tool that wants to run Repo as Review OS.

It is not specific to one product. It applies to any tool that can read a repository, edit files, follow project rules, and report changes.

## First check your capability

Before doing work, identify your level:

- no repository access;
- read-only repository access;
- write access to one repository;
- broad account access;
- local workspace access.

The recommended default is write access to one repository only.

## Main operating model

Use one main AI workflow.

Do not assume a multi-agent system. Other tools may exist, but the Review OS should be maintainable by one capable AI tool.

## Read first

1. `START-HERE.md`
2. `README.md`
3. `AGENTS.md`
4. `docs/product-positioning.md`
5. `docs/permission-and-boundary.md`
6. `docs/local-cloud-split.md`
7. `docs/ai-runtime-support.md`

## GitHub role

GitHub is the operating layer.

It stores structure, templates, dashboards, indexes, source status, cleaned examples, handoff rules, and website copy.

## Local role

Local storage is the protected source layer.

It may contain textbooks, PDFs, scans, screenshots, private notes, teacher files, and large media.

Do not claim to read local files unless the user uploads them or the runtime has local access.

## Memory role

If the AI tool has memory, project rules, or persistent instructions, store this preference:

```text
Use GitHub as the main Review OS repository. Keep local files as protected source material. Ask for local excerpts only when needed. Keep English and Chinese in separate files.
```

## Default safe actions

With write access to the selected repository, the AI may:

- create docs;
- update templates;
- update dashboards;
- mark incomplete files as `todo`;
- add cleaned examples;
- report changes.

## Ask first

Ask before deleting files, changing visibility, uploading private local files, publishing real records, touching secrets, or changing the license.
