# Quickstart

Use this page if you want to try GitLearnOS but do not want to read the whole repository first.

## What you need

You need four things:

```text
this template repository
+ your own target GitHub repository
+ one AI tool that can read the template and write to the target
+ one learning goal
```

The target repository is where your personal learning records will live.

The AI tool can be ChatGPT with a GitHub connector, Codex, Claude Code, Cursor, Windsurf, or another agent connected through MCP or a GitHub integration.

## Five-minute setup

### 1. Create a private target repository

For first deployment, create an empty or nearly empty private repository, then let the AI set up the GitLearnOS structure inside it.

If you already have files in the target repository, tell the AI to inspect the existing files first and avoid overwriting them.

Use a private repository if you will store real study notes, mistakes, screenshots, scores, or personal learning records.

Suggested name:

```text
my-gitlearnos
```

### 2. Connect your AI tool to the target repository

Use MCP, a GitHub connector, or another safe integration.

Grant access to one repository first. Do not grant broad account access unless you understand the risk.

The AI should confirm whether it can actually read and write the target repository. If it cannot, it should say so clearly.

### 3. Send this prompt to your AI tool

```text
Read this template repository:
https://github.com/Guojiz/Repo-as-Review-OS

Set up my own personal GitLearnOS in this target repository:
<paste your repository link>

This is a first deployment. Treat the target repository as empty or nearly empty unless you find existing files. If existing files are present, inspect them first and do not overwrite them without asking.

Start with START-HERE.md, README.md, QUICKSTART.md, docs/first-experiment-guide.md, docs/what-goes-into-github.md, docs/runtime-self-adaptation.md, AGENT-RUNTIME.md, AGENTS.md, docs/skill-and-memory-runtime.md, docs/adaptive-memory-and-learner-profile.md, and docs/lightweight-skg-dpm.md.

If you support skills, use skills/repo-as-review-os/SKILL.md. If not, use the memory fallback from docs/skill-and-memory-runtime.md.

Create a minimal learning repository with dashboard.md, learner-profile.md, goals/main-goal.md, sources/, models/, knowledge-gaps/, reviews/, templates/, agents/, automations/, and archive/. Ask me for my first learning goal before creating detailed content. Report every file you create or edit.
```

### 4. Tell the AI your first goal

Examples:

```text
I want to improve SAT Reading and Writing in 6 weeks.
```

```text
I want to review my math mistakes every week.
```

```text
I want to read three AI papers and remember the main ideas.
```

```text
I want to organize my daily English learning.
```

### 5. Use it normally

After setup, you can say things like:

```text
Based on my repository, make me a 30-minute review set.
```

```text
Turn this mistake into a reusable model, record the knowledge gap, and schedule review.
```

```text
Check my dashboard and tell me what I should study today.
```

```text
Generate a short practice test from my knowledge gaps.
```

## What goes into GitHub

GitHub mainly stores structured learning records: goals, learner profile, source records, reusable models, knowledge gaps, review sets, dashboards, next review dates, and handoff notes.

It does not have to store every original file. See [docs/what-goes-into-github.md](docs/what-goes-into-github.md).

## What not to upload

Do not upload private or copyrighted material into a public repository.

Avoid uploading:

- full textbook pages;
- full test questions from copyrighted sources;
- teacher files;
- private screenshots;
- score reports;
- IDs, passwords, tokens, or cookies.

For real learning data, use a private repository.

## What success looks like

After setup, your repository should have:

```text
dashboard.md
learner-profile.md
goals/main-goal.md
sources/
models/
knowledge-gaps/
reviews/
templates/
agents/
automations/
archive/
```

The AI should be able to answer:

```text
What is my current goal?
What knowledge gaps are active?
What should I review next?
What practice should I do today?
What files did you change?
```

## Choose a demo

If you want an example first, start here:

- [examples/en/demo-sat-lite/](examples/en/demo-sat-lite/)
- [examples/en/demo-research-reading-lite/](examples/en/demo-research-reading-lite/)
- [examples/zh-CN/demo-zhongkao-lite/](examples/zh-CN/demo-zhongkao-lite/)