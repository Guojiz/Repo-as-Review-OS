# FAQ

## What is Repo as Review OS?

Repo as Review OS is a GitHub-based learning repository protocol.

It helps an AI tool organize goals, source records, reusable models, review sets, dashboards, and handoff notes in one target repository.

## Is this repository my learning repository?

No.

This repository is the template repository.

Your own target repository is where your personal learning records should go.

## What is the first thing I should do?

Create an empty or nearly empty private target repository, then ask an AI tool to read this template repository and deploy the minimal structure into your target repository.

Start with [QUICKSTART.md](QUICKSTART.md).

## Can it organize my learning data into GitHub?

Yes.

It organizes structured learning records into GitHub: goals, source records, reusable models, review sets, dashboards, next review dates, and handoff notes.

It does not require every original file to be uploaded.

See [What Goes Into GitHub](docs/what-goes-into-github.md).

## Do I have to upload all my files?

No.

Large files, original screenshots, textbook pages, raw exports, and local working files can stay outside GitHub when needed.

GitHub should keep the structured learning state.

## Can I use it locally?

Yes, but local use is not identical to a GitHub-backed Review OS.

A local workspace can test the method and edit local files. It does not automatically mean the AI has GitHub access.

See [Local Runtime Note](docs/local-runtime-note.md).

## Does it require GitHub Actions?

No.

GitHub Actions can be an optional advanced layer, but basic setup does not require it.

## Does it require API keys?

No.

Basic use can work with an AI tool that has repository access through a connector, MCP, or local workspace. API keys are only for advanced custom automation.

## Which AI tools can run it?

Any AI tool that can read the template, access the target repository, edit files, and report changes can run it.

Examples include ChatGPT with a GitHub connector, Codex, Claude Code, Cursor, Windsurf, MCP workers, or other repository-aware agents.

## How do I know whether the AI really has GitHub access?

Ask it to identify its runtime and permission boundary before setup.

It should say whether it can:

- read the template repository;
- read the target repository;
- write to the target repository;
- use local files only;
- needs you to complete a manual setup step.

It should not claim GitHub changes unless it can report the actual files changed.

## What should success look like?

After setup, the target repository should contain:

```text
dashboard.md
goals/main-goal.md
sources/
models/
reviews/
templates/
agents/
automations/
archive/
```

Then the AI should ask for your first learning goal.
