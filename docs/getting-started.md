# Getting Started

This page is a short entry point for human users.

For the full first setup flow, start with:

- [QUICKSTART.md](../QUICKSTART.md)
- [First Experiment Guide](first-experiment-guide.md)
- [What Goes Into GitHub](what-goes-into-github.md)
- [Runtime Self-Adaptation](runtime-self-adaptation.md)

## The basic idea

Repo as Review OS uses two repositories roles:

```text
Repo as Review OS repository
→ template repository
→ method, docs, skills, examples, rules

Your target repository
→ personal learning repository
→ goals, sources, models, reviews, dashboard
```

Do not write personal learning data into the template repository.

## First setup

1. Create an empty or nearly empty private target repository.
2. Connect an AI tool that can read the template and write to the target.
3. Ask the AI to identify its runtime and permission boundary.
4. Ask it to create the minimal structure in the target repository.
5. Give it your first learning goal.

## Minimal target structure

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

## Important boundary

A local workspace can test the method, but it is not the same as a GitHub-backed Review OS.

The AI must not claim GitHub write access, push, Issues, or remote updates unless it has verified those abilities.

See [Local Runtime Note](local-runtime-note.md).
