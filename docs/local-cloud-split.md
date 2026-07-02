# Local and Cloud Split

Repo as Review OS should separate what belongs on the user's local machine from what belongs in GitHub.

## Core principle

GitHub is the shared operating layer. Local storage is the protected source layer.

## Put in GitHub

GitHub should store:

- README files;
- AGENTS files;
- handoff rules;
- dashboards;
- indexes;
- templates;
- cleaned examples;
- source status notes;
- links or references to local-only material;
- generated review plans;
- public website copy.

GitHub is for structure, state, and reusable method.

## Keep local

Local storage should keep:

- original textbooks;
- copyrighted PDFs;
- raw scans;
- personal screenshots;
- teacher files;
- private notes;
- large media files;
- files the AI cannot access safely.

Local storage is for protected source material.

## How to reference local material

Do not upload private or copyrighted sources by default.

Instead, create a source record in GitHub:

```text
Status: local-only-source
Local reference: textbook chapter, page, or file name
Public summary: short safe description
Needed action: user must upload excerpt or screenshot if AI needs it
```

## AI behavior

The AI should:

1. use GitHub as the main map;
2. check whether a needed source is online or local-only;
3. ask the user to upload only the needed excerpt;
4. never pretend it has read a local file it cannot access;
5. write back cleaned notes, models, and indexes to GitHub.

## Single-AI flow

```text
User → ChatGPT → GitHub repository
             ↘ asks user for local excerpt only when needed
```

No extra local agent is required.

## Difference from the old system

The old system could rely on a local agent to inspect files, pull tasks, and push results. This template assumes that the main AI is ChatGPT or a similar single AI. Therefore, local-only materials must be surfaced by the user when needed.
