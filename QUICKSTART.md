# Quickstart

Use this page if you want to try Repo as Review OS but do not want to read the whole repository first.

## What you need

You need three things:

```text
one GitHub repository
+ one AI tool that can read or write GitHub
+ one learning goal
```

The AI tool can be ChatGPT with a GitHub connector, Codex, Claude Code, Cursor, Windsurf, or another agent connected through MCP or a GitHub integration.

## Five-minute setup

### 1. Create a private GitHub repository

Use a private repository if you will store real study notes, mistakes, screenshots, scores, or personal learning records.

Suggested name:

```text
my-learning-os
```

### 2. Connect your AI tool to that repository

Use MCP, a GitHub connector, or another safe integration.

Grant access to one repository first. Do not grant broad account access unless you understand the risk.

### 3. Send this prompt to your AI tool

```text
Read https://github.com/Guojiz/Repo-as-Review-OS and help me set up my own personal learning OS in this repository: <paste your repository link>.

Start with START-HERE.md, README.md, OPERATING-MODEL.md, AGENT-RUNTIME.md, AGENTS.md, and docs/skill-and-memory-runtime.md.

If you support skills, use skills/repo-as-review-os/SKILL.md. If not, use the memory fallback from docs/skill-and-memory-runtime.md.

Create a minimal learning repository with dashboard.md, goals/main-goal.md, sources/, models/, reviews/, templates/, agents/, automations/, and archive/. Ask me for my first learning goal before creating detailed content. Report every file you create or edit.
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
Turn this mistake into a reusable model and schedule review.
```

```text
Check my dashboard and tell me what I should study today.
```

```text
Generate a short practice test from my weak points.
```

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
goals/main-goal.md
sources/
models/
reviews/
templates/
agents/
automations/
archive/
```

The AI should be able to answer:

```text
What is my current goal?
What am I weak at?
What should I review next?
What practice should I do today?
What files did you change?
```

## Choose a demo

If you want an example first, start here:

```text
examples/en/demo-sat-lite/
examples/en/demo-research-reading-lite/
examples/zh-CN/demo-zhongkao-lite/
```
