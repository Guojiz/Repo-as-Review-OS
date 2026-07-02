# Skills

Repo as Review OS can be used as one broad skill or as a small skill suite.

The recommended structure is:

```text
repo-as-review-os                  Main router
repo-as-review-os-setup            Create or migrate a learning repository
repo-as-review-os-source           Turn materials into source records
repo-as-review-os-model            Extract reusable learning models
repo-as-review-os-review           Generate review sets and mini tests
repo-as-review-os-maintenance      Audit and maintain the repository
```

## Why multiple skills?

A single large skill is easy to install but can be too broad.

Smaller skills help an AI agent load the right behavior for the task:

- setup when creating a repository;
- source when recording materials;
- model when extracting reusable understanding;
- review when generating practice;
- maintenance when cleaning or auditing the repository.

## Recommended usage

Start with the router:

```text
skills/repo-as-review-os/SKILL.md
```

Then use the specific subskill when the task is clear.

## If your AI tool does not support multiple skills

Use only the router skill.

If your AI tool does not support skills at all, use the memory fallback in:

```text
docs/skill-and-memory-runtime.md
```

## Important distinction

Skills give behavior.

Memory gives stable preferences.

Repository files store current learning state.
