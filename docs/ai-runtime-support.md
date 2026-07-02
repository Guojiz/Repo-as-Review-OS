# AI Runtime Support

Repo as Review OS is not tied to one AI product.

It can be supported by any AI tool that can read instructions, access a repository, edit files, and report changes.

## Required capabilities

A good runtime should provide:

1. repository access;
2. file creation and editing;
3. project rules or long-term memory;
4. permission boundaries;
5. optional local workspace access;
6. change reporting.

## Possible runtimes

This system may be used with tools such as:

- ChatGPT with GitHub or MCP connectors;
- Codex-style coding agents;
- Claude Code-style command-line tools;
- Cursor or Windsurf-style AI editors;
- other repository-aware AI tools.

The project should describe capabilities, not force one brand.

## Why memory matters

The AI should remember this user preference:

```text
Use GitHub as the main Review OS repository. Treat local files as protected source material. Ask for local excerpts only when needed. Keep English and Chinese in separate files.
```

Without memory or project instructions, the user has to repeat the same setup in every conversation.

## Minimum runtime

```text
one AI tool + one GitHub repository + one rule file
```

## Best runtime

```text
one main AI tool
+ GitHub repository connector
+ project memory or persistent instructions
+ clear permission boundary
+ optional local file upload when needed
```

## Obsidian path

Some users may start with Obsidian. A practical migration path is:

```text
Obsidian
→ Obsidian + Git
→ Obsidian + Git + GitHub
→ GitHub + one AI tool
```

The final form is simpler because the user can manage the system from one AI app and one GitHub repository.
