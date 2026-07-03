# Local and Cloud Split

This page is a supplementary guide.

For the current main guides, read:

- [What Goes Into GitHub](what-goes-into-github.md)
- [Local Runtime Note](local-runtime-note.md)
- [Runtime Self-Adaptation](runtime-self-adaptation.md)

## Core principle

GitHub is the operating layer.

Local storage is the working/source layer.

Do not collapse them into one place.

## Put in GitHub

GitHub should store structured learning records:

- goals;
- source records;
- dashboards;
- indexes;
- templates;
- reusable models;
- review plans;
- next review dates;
- handoff notes.

GitHub is for structure, state, and reusable method.

## Keep local when needed

Local storage may keep:

- large files;
- original screenshots;
- textbook pages;
- raw scans;
- private notes;
- local working files;
- raw exports from other apps.

Local storage is for original working material.

## How to reference local material

If a source stays outside GitHub, create a source record in GitHub:

```text
Status: local-only-source
Local reference: folder, page, or file name
Visible excerpt: what the AI has actually seen
Needed action: ask user for an excerpt if more detail is needed
```

## AI behavior

The AI should:

1. use GitHub as the main map;
2. check whether a needed source is available or local-only;
3. ask the user for only the needed excerpt;
4. never pretend it has read a local file it cannot access;
5. write cleaned notes, models, indexes, and review records back to the target repository.

## Local runtime warning

A local workspace can reproduce part of the method, but it is not identical to a GitHub-backed Review OS.

If the AI has only local file access, it must not claim that GitHub setup, push, Issues, or remote updates have happened.

See [Local Runtime Note](local-runtime-note.md).
