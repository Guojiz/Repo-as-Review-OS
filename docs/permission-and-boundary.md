# Permission and Boundary Model

Repo as Review OS should start by asking one question:

**What can the AI actually read and change without asking again?**

A review system fails when the AI does not understand its permission boundary.

## 1. Permission levels

### Level 0: no repository access

The AI can only explain the idea and give instructions. It cannot inspect or edit files.

### Level 1: read-only repository access

The AI can inspect the repository and suggest changes, but cannot write files.

### Level 2: write access to one repository

The AI can create and edit files in one selected repository. This is the recommended default.

### Level 3: broad account access

The AI can reach many repositories or connected services. This is powerful but risky. Avoid this unless there is a strong reason.

## 2. Recommended default

Use Level 2:

- one repository;
- read and write access;
- no account-wide permission;
- no secret access;
- no destructive operations.

This gives the AI enough power to work smoothly while keeping the boundary clear.

## 3. Low-friction operation

To reduce repeated permission clicks, the user should:

1. create or choose one Review OS repository;
2. authorize the AI tool for that repository;
3. allow normal file creation and editing inside that repository;
4. require a report after changes;
5. keep destructive actions blocked.

## 4. Actions the AI may do without asking

If it has write access to the selected repository, the AI may:

- create missing docs;
- create templates;
- update indexes;
- mark incomplete files as `todo`;
- add cleaned examples;
- update dashboards;
- record what changed.

## 5. Actions that require confirmation

The AI must ask before it:

- deletes files;
- changes repository visibility;
- force pushes;
- uploads local private files;
- publishes real study records;
- changes license;
- touches secrets, tokens, cookies, or credentials.

## 6. Single-AI model

This project assumes one main AI, such as ChatGPT, acts as the maintainer.

Do not require a multi-agent workflow. Other tools may exist, but the main model should be able to read the repository, make decisions, edit files, and report changes.

## 7. What cannot be made fully invisible

Some actions will always need user confirmation because platforms protect the user:

- first-time GitHub connection;
- repository permission grant;
- high-risk writes;
- local file access;
- publishing or changing visibility.

The goal is not zero permission prompts. The goal is to set one clear repository boundary so normal maintenance does not require constant approval.
