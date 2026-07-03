# Runtime Self-Adaptation

Repo as Review OS should not assume every AI tool works the same way.

The repository gives the protocol. The current AI environment decides how that protocol can actually be deployed.

## Core rule

```text
Identify the runtime before deployment.
Then adapt the setup path to that runtime.
```

## First questions for the AI

Before setting up a user's repository, the AI should answer:

```text
What environment am I running in?
Can I read the target repository?
Can I write to the target repository?
Do I support skills?
Do I rely on memory or project instructions instead?
Can I use a local workspace?
Which steps must the user complete manually?
```

## Use current product guidance when needed

If deployment depends on a specific AI app, connector, project system, workspace, or permission flow, the AI should not guess.

It should use current product guidance when available, or ask the user to complete the needed manual step.

The AI should say clearly:

```text
I cannot perform this step from here. Please complete it manually, then tell me when it is done.
```

## Runtime-specific deployment

Different environments may use different setup paths:

```text
ChatGPT Project
→ project instructions, memory fallback, optional GitHub connector, local subject folders

Codex
→ repository setup, file edits, template copying, structured handoff

Claude Code / Cloud
→ workspace-based repository work if available

Cursor / Windsurf
→ local workspace edits and repository maintenance

MCP worker
→ explicit tool-based execution

GitHub Actions
→ deterministic checks and simple reports
```

## Deployment response pattern

When an AI starts setup, it should output:

```text
Runtime detected:
- environment:
- read access:
- write access:
- skill support:
- memory or project-instruction fallback:
- user steps needed:

Deployment plan:
1. confirm target repository
2. check whether it is empty or already has files
3. choose skill or memory fallback
4. create or verify structure
5. ask for the first learning goal
6. report changes
```

## Principle

Repo instructions are the map.

The current AI runtime is the vehicle.

The AI should preserve the Repo as Review OS protocol while adapting the actual setup path to its own tools.
