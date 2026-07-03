# Automation Runtime Matrix

Repo as Review OS does not require one fixed automation engine.

Automation is an execution interface that can be implemented differently depending on the AI environment.

## Core rule

```text
Same repository protocol.
Different runtime abilities.
```

The repository should define:

- where goals live;
- where sources live;
- where models live;
- where reviews live;
- where automation outputs should go;
- what the AI must not claim without tool access.

The runtime decides how much can actually be executed.

## Runtime matrix

| Runtime | Best role | Can read/write repository? | Recommended use |
|---|---|---:|---|
| ChatGPT scheduled automation | Prompt-only handoff | Usually no | Send a starter card and ask the user to continue in a tool-enabled chat. |
| ChatGPT with GitHub connector | Interactive worker | Yes, when connected | Read repository state, edit files, and report changes inside the current conversation. |
| Codex | Repository worker | Yes, when granted access | Set up structure, edit files, run code, and perform focused repository tasks. |
| Claude Code / Cloud | Repository worker | Depends on setup | Run longer coding or repository-maintenance workflows if connected to the repo. |
| Cursor / Windsurf | IDE worker | Yes, inside the workspace | Edit files locally, apply templates, and help maintain the learning repository. |
| MCP worker | Tool worker | Yes, if configured | Act as a real automation worker with explicit tool permissions. |
| GitHub Actions | Script worker | Yes, but scripted | Run deterministic checks, generate simple reports, and validate repository structure. |
| Manual agent prompt | Human-triggered worker | Depends on current tool | Let the user paste a handoff prompt into whichever AI currently has access. |

## What should not be assumed

Do not assume every AI tool can:

- access GitHub;
- edit files;
- run scripts;
- preserve state across runs;
- inspect local-only materials;
- generate final review sets without reading the repository first.

## Prompt-only automation

Use this when the automation environment is only a scheduled prompt.

It should produce:

```text
handoff card
next command
repository areas to inspect
risks to verify
clear warning that no repository work has been completed yet
```

It should not produce final repository outputs.

## Worker automation

Use this when the environment has repository or tool access.

It may:

```text
read dashboard
read active goal
read source records
read models
create review output
update dashboard
write an automation report
report changed files
```

## Optional GitHub Actions layer

GitHub Actions can be useful, but it should not be required.

A lightweight GitHub Actions worker may check:

```text
dashboard.md exists
goals/main-goal.md exists
sources/ exists
models/ exists
reviews/ exists
templates/ exists
automations/ exists
```

This is a structure check, not a replacement for an AI learning agent.

## Positioning

Repo as Review OS is a portable learning repository protocol first.

It can support scripts, GitHub Actions, and scheduled workers, but it should not be locked to one automation engine.
