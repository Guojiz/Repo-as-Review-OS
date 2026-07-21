# First Experiment Guide

Use this guide when someone wants to try Repo as Review OS for the first time and is confused about which repository to use.

## The two-repository mental model

```text
Repo as Review OS repository
→ template repository
→ method, docs, skills, examples, rules

Your own empty repository
→ personal learning repository
→ your goals, sources, models, reviews, dashboard
```

Do not write personal learning data into the template repository.

The AI should read the template repository, then deploy the structure into the user's own repository.

## Recommended first experiment

1. Create a new empty private repository.
2. Give the AI the Repo as Review OS link.
3. Give the AI the empty target repository link.
4. Ask the AI to identify its runtime and permissions.
5. Ask the AI to deploy the minimal structure.
6. Give the AI the first learning goal.

## Prompt for ChatGPT

```text
Read this template repository:
https://github.com/Guojiz/GitLearnOS

Deploy the minimal Repo as Review OS structure into my empty target repository:
<paste target repository link>

First identify your runtime and permission boundary:
- can you read the template repository?
- can you read the target repository?
- can you write to the target repository?
- do I need to manually enable any connector or permission?

Do not overwrite existing files without asking.
After setup, ask for my first learning goal.
```

## Prompt for Codex or a local coding agent

```text
Use the Repo as Review OS repository as the template and documentation source.
Use my new empty repository or local folder as the target learning repository.

Do not write personal learning data into the template repository.

Create the minimal structure in the target:
- dashboard.md
- goals/main-goal.md
- sources/
- models/
- reviews/
- templates/
- agents/
- automations/
- archive/

Report every file created or edited.
Then ask for my first learning goal.
```

## If using a local copy

A local setup should still keep the same roles:

```text
local copy of Repo as Review OS
→ reference template

local my-learning-os folder
→ target learning repository
```

The AI may read the template folder, but it should write learning state into the target folder.

## What should happen after setup

The target repository should contain:

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

The AI should then ask:

```text
What is the first learning goal you want this repository to support?
```

## Common confusion

```text
Wrong:
Use the Repo as Review OS repository itself as my learning repository.

Correct:
Use Repo as Review OS as the template and deploy its structure into my own repository.
```

```text
Wrong:
Send one problem before setup and expect the AI to know where to write.

Correct:
Deploy the target repository first, then send goals, problems, notes, or review tasks.
```

```text
Wrong:
Assume every AI tool connects to GitHub in the same way.

Correct:
Ask the AI to identify its runtime and tell the user which manual steps are needed.
```
