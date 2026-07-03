# Local Runtime Note

Repo as Review OS can run across three layers:

```text
GitHub repository
→ learning structure, indexes, models, reviews, dashboard, agent rules

AI project space
→ project instructions, current conversation context, selected working inputs

Local folders
→ original learning files and subject folders kept outside the repository
```

## For ChatGPT Plus users

A user does not always need Codex for daily learning.

A practical setup can be:

```text
ChatGPT Project
+ Repo as Review OS instructions
+ GitHub repository
+ local subject folders
```

ChatGPT can handle many daily tasks when the GitHub connector or another safe writeback path is available.

Codex or another coding agent is useful for larger repository operations, but it is not required for every review session.

## Suggested local folders

```text
Learning-OS-Local/
├── Chinese/
├── Math/
├── English/
├── Physics/
├── History/
└── _shared/
```

Each subject folder may contain the user's own working files, notes, and selected excerpts for AI use.

## Repository link to local folders

If an important source stays outside GitHub, create a source record in GitHub:

```text
status: local-only-source
subject: Math
where it lives: local Math folder
what AI can see: selected excerpt only
```

The AI must not pretend it has read a local-only source.

It should ask for the relevant excerpt or mark the source as incomplete.

## Positioning

GitHub is the operating layer.

The AI project is the conversation layer.

Local folders are the protected working layer.

Do not collapse all three into one place.
