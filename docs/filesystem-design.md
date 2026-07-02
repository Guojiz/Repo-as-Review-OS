# Filesystem Design

Repo as Review OS should use the file system as its interface.

The AI should not only write Markdown content. It should use folders, filenames, dates, status labels, indexes, and archives to make the repository readable.

## Why file structure matters

A good file tree lets both humans and AI understand the system quickly.

The structure should answer:

- what is active;
- what is archived;
- what is a source;
- what is a model;
- what needs review;
- what needs user input.

## Recommended structure

```text
review-os/
├── dashboard.md
├── inbox/
├── sources/
├── models/
├── reviews/
├── templates/
├── agents/
├── automations/
└── archive/
```

## Folder roles

- `inbox/`: new material waiting to be processed.
- `sources/`: source records and references.
- `models/`: reusable patterns extracted from problems or notes.
- `reviews/`: generated practice sets and review logs.
- `templates/`: reusable file templates.
- `agents/`: AI handoff and runtime rules.
- `automations/`: scheduled outputs and automation logs.
- `archive/`: old or inactive material.

## Naming rules

Use names that carry meaning:

```text
YYYY-MM-DD_topic_status.md
```

Examples:

```text
2026-07-02_geometry-similarity_model.md
2026-07-02_weekly-review_todo.md
2026-07-02_source-local_textbook-reference.md
```

## Status labels

Recommended labels:

- `source`
- `summary`
- `model`
- `index`
- `todo`
- `local-only-source`
- `archived`

## AI behavior

Before adding a file, the AI should decide:

1. Which folder does it belong in?
2. Is it source, summary, model, index, or todo?
3. Does the filename include enough meaning?
4. Should an index or dashboard be updated?
5. Should old files be archived instead of duplicated?

## Practical rule

The file tree is part of the product. Keep it clean enough that a new AI can understand it without reading every file.
