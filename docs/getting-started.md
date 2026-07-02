# Getting Started

This guide is for a human user who wants ChatGPT, Codex, or another AI tool to help build a Review OS repository.

## 1. Create a GitHub repository

1. Open GitHub.
2. Click **New repository**.
3. Choose a name, for example `my-review-os`.
4. Start private if you will store real study records.
5. Add a license if you want others to reuse it.

Recommended license for a public template: MIT License.

## 2. Give AI access

If you use ChatGPT with GitHub tools, connect GitHub and allow access to the repository.

If you use Codex, open the repository as the project workspace and make sure it can read and edit files.

Use the least privilege that still works. Start with one repository, not your whole account.

## 3. First prompt to AI

```text
Read README.md and AGENTS.md first. Help me initialize this repository as a Review OS. Keep all personal study records private. Create or update docs, agents, templates, and website copy. Keep English and Chinese in separate files.
```

## 4. What to add first

Add these files or folders first:

- `AGENTS.md`
- `README.md`
- `docs/architecture.md`
- `docs/privacy-and-sourcing.md`
- `agents/handoff-protocol.md`
- `templates/problem-card.md`
- `templates/dashboard.md`

## 5. Private first, public later

A real review repository may contain personal learning records. Keep it private first.

When publishing, extract only:

- structure;
- templates;
- fake examples;
- method notes;
- deployment instructions.
