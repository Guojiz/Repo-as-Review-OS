# Repo as Review OS

A deployable review-system template built on GitHub and Markdown.

The idea is simple: treat a repository as the operating system for study. Notes, mistakes, reusable methods, writing drafts, source checks, and handoff rules should live in one structured place instead of being scattered across chats and screenshots.

## Goals

- Keep original sources traceable.
- Turn mistakes into reusable models.
- Separate originals, summaries, indexes, and TODO items.
- Give future tools a clear map before they edit anything.
- Publish only cleaned and non-private method-level content.

## Suggested layout

```text
Repo-as-Review-OS/
├── README.md
├── LICENSE
├── docs/
├── agents/
├── templates/
└── website/
```

## Main layers

- `docs/`: architecture, deployment, privacy, and sourcing notes.
- `agents/`: handoff rules and maintenance protocols.
- `templates/`: reusable cards for problems, writing materials, daily review, and dashboards.
- `website/`: public page copy for a personal site or project page.

## Minimum workflow

1. Add a source, mistake, draft, or feedback item.
2. Mark its status: original, summary, index, model, or TODO.
3. Convert reusable items into templates.
4. Use the handoff rules before editing the repository.
5. Deploy only cleaned public-facing content.

## License

MIT License. See `LICENSE`.
