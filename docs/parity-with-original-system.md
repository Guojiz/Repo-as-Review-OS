# Parity with the Original System

This document checks whether GitLearnOS can reproduce the behavior of the original `zhongkao` repository system.

The original `zhongkao` system is the primary practical baseline for this project. External tutoring research can inspire design checks, but the first standard is whether the real learning loop that already worked can be made lighter, reusable, and easier for other AI tools to deploy.

The repository is still named `Repo-as-Review-OS` for continuity.

## What can be reproduced

### 1. GitHub as the main operating layer

Yes. The new template can use GitHub as the main map, state store, template library, and handoff surface.

### 2. AI-first maintenance

Yes. The original system moved toward ChatGPT as the main maintainer. GitLearnOS makes this explicit through `START-HERE.md`, `AGENTS.md`, and the handoff protocols.

### 3. Content integrity

Yes. The old system protected the difference between source, summary, index, and incomplete files. GitLearnOS reproduces this through sourcing rules, content labels, and local-only source records.

### 4. Templates and dashboards

Yes. Problem cards, writing material cards, daily review files, knowledge-gap records, and dashboards can all be reproduced.

### 5. Review and next-action loop

Yes. The useful loop is preserved:

```text
goal
→ source
→ split
→ model
→ knowledge gap
→ review set
→ dashboard
→ next action
```

## What cannot be fully reproduced by GitHub alone

### 1. Fully invisible local inspection

If the AI cannot access local files, it cannot inspect textbooks, screenshots, PDFs, or private notes by itself.

### 2. Automatic background execution

A single AI in a chat app usually cannot run forever in the background. It can maintain the repository during a session, but scheduled or background tasks depend on the platform.

### 3. Permission prompts

The AI cannot remove all permission prompts. First-time connection, repository authorization, local file access, deletion, and publishing still need user approval.

## New recommended model

The new template should not require a multi-agent system.

Recommended model:

```text
ChatGPT or one main AI
→ GitHub repository
→ user supplies local excerpts only when needed
```

## Why this is different from the old system

The old system experimented with local agents, Obsidian, Git, GitHub, and automated inspection.

GitLearnOS is simpler:

- one main AI;
- one GitHub repository;
- clear permission boundary;
- local protected source files;
- GitHub as the shared operating layer;
- ChatGPT memory or project instructions as the personal preference layer.

## Practical conclusion

GitLearnOS can reproduce the old system's structure and method.

It cannot perfectly reproduce invisible local automation unless the user adds a local agent or grants local file access.

Therefore, the default product should promise this:

**A lightweight GitHub + AI learning system that works from one repository and one main AI, with local files surfaced only when needed.**
