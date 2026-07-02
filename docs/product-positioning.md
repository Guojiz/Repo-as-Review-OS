# Product Positioning

Repo as Review OS is an AI-native review system built around GitHub.

It is not a ChatGPT-only project. It is not an Obsidian-only workflow. It is not a multi-agent framework.

It is a lightweight operating model for one main AI tool and one GitHub repository.

## One sentence

Use GitHub as the review system, and use one capable AI tool to maintain it.

## What makes it work

The system works when the AI tool has these capabilities:

1. read repository files;
2. create and edit files;
3. follow project rules such as `AGENTS.md`;
4. remember user preferences through memory, project rules, or persistent instructions;
5. respect permission boundaries;
6. report every change.

The specific AI product is not the point. The capability set is the point.

## Why GitHub instead of Obsidian as the final layer

Many users start with Obsidian because it feels like a natural knowledge base.

A practical path may look like this:

```text
Obsidian
→ Obsidian + Git
→ Obsidian + Git + GitHub
→ GitHub + one AI tool
```

The final form is simpler:

- no extra local app is required for the core workflow;
- the repository itself becomes the shared source of truth;
- version history is built in;
- AI tools can read and edit the same structure;
- the user can manage the system from one AI app plus one repository connector.

Obsidian can still be useful as a personal editor, but it is no longer the center of the system.

## Core runtime

Minimum runtime:

```text
one AI tool + one GitHub repository + one rule file
```

Best runtime:

```text
one main AI tool
+ GitHub or MCP connector
+ memory or project instructions
+ single-repository write access
+ clear safety boundary
```

## What goes online

GitHub should contain:

- structure;
- templates;
- dashboards;
- indexes;
- source status notes;
- cleaned examples;
- handoff rules;
- website copy.

GitHub is the operating layer.

## What stays local

Local storage should keep:

- textbooks;
- copyrighted PDFs;
- raw scans;
- private screenshots;
- teacher files;
- large media;
- anything the user does not want to upload.

Local storage is the protected source layer.

## How AI should handle local files

The AI must not pretend it has read local files.

If a source is local-only, the AI should create a source record in GitHub and ask the user for the smallest needed excerpt when necessary.

## Permission philosophy

The best default is one-repository write access.

This lets the AI work smoothly inside the Review OS repository while keeping risky actions blocked.

Safe default actions:

- create docs;
- update templates;
- update dashboards;
- mark incomplete files as `todo`;
- add cleaned examples;
- report changes.

Ask before:

- deleting files;
- changing visibility;
- uploading private local files;
- publishing real study records;
- touching secrets;
- changing the license.

## Final promise

Repo as Review OS lets a user run a review system with:

```text
one AI app
one GitHub repository
one connector
one memory or project-rule layer
```

It reduces the workflow from many tools to one durable repository that an AI can understand and maintain.
