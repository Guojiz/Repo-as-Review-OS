# Deploy OpenHanako with Claude Code or Codex

This guide explains the role of Claude Code, Codex, Cursor, or another coding agent in the GitLearnOS ecosystem.

They are not the daily GitLearnOS learning runtime maintained by this repository.

They can be useful for one specific job:

```text
deploy, inspect, debug, and customize OpenHanako / HanaAgent
```

After OpenHanako is running, the GitLearnOS desktop workflow should run inside OpenHanako through its native Agent, subagent, channel, desk, memory, Skills, and scheduled-task capabilities.

## Boundary

```text
ChatGPT
→ daily GitLearnOS learning platform

OpenHanako / HanaAgent
→ desktop multi-agent runtime for local files and deeper automation

Claude Code / Codex / Cursor / CLI agents
→ deployment and source-code assistant for OpenHanako, not the maintained daily learning layer
```

Do not ask Claude Code or Codex to become the GitLearnOS tutoring platform unless the user intentionally wants a developer workflow.

Use them to read OpenHanako source, install dependencies, run scripts, diagnose build errors, and prepare a local OpenHanako setup.

## What the OpenHanako source shows

OpenHanako is an Electron + React + Vite + Node application.

The root `package.json` declares:

```text
name: hanako
main: desktop/bootstrap.cjs
bin: hana → cli/entry.ts
Node engine: >=24.12.0 <25
```

Important scripts include:

```text
npm run start
npm run start:dev
npm run start:vite
npm run cli
npm run server
npm run build:client
npm run build:server
npm run pack
npm run dist
npm run dist:win
npm run dist:linux
npm run typecheck
npm run test
```

The project builds renderer, preload, theme, main, server, computer-use helper, and platform installers through scripts in `package.json`.

## Source-level deployment facts

### Node version matters

OpenHanako requires Node `>=24.12.0 <25` at the project level.

The server distribution build also pins a bundled Node runtime, currently `v24.15.0`, and verifies runtime checksums before packaging.

A deployment agent should check Node first:

```bash
node -v
npm -v
```

If the Node version is wrong, fix Node before debugging app code.

### Development launcher matters

OpenHanako uses `scripts/launch.js` as a cross-platform launcher for Electron, dev Electron, CLI, and server modes.

That launcher intentionally clears `ELECTRON_RUN_AS_NODE` before spawning Electron, because VS Code or Claude Code terminals may set it and break Electron startup.

This is why Claude Code can be helpful for deployment, but also why the deployment instructions should use the repository scripts rather than raw Electron commands.

### Dev data location

`scripts/dev-env.js` sets development data under:

```text
~/.hanako-dev
```

Production data uses `HANA_HOME`, documented in the OpenHanako README as production defaulting to `~/.hanako` and development defaulting to `~/.hanako-dev`.

A deployment agent should not delete these folders without asking.

### Server architecture

The server is a Hono HTTP + WebSocket API and can run either independently or as a forked process inside the Electron desktop app.

It registers routes for chat, sessions, models, agents, desk, skills, channels, DM, filesystem, preferences, bridge, commands, resources, mobile workbench, media, and more.

For GitLearnOS, this means OpenHanako is not just a chat UI. It is a local agent server with file, agent, channel, desk, skill, and automation surfaces.

## Deployment checklist for code agents

A Claude Code / Codex deployment agent should follow this order:

```text
1. Clone or open liliMozi/openhanako.
2. Confirm OS and CPU architecture.
3. Confirm Node version is >=24.12.0 and <25.
4. Run npm install.
5. Run npm run typecheck.
6. Run npm test if time allows.
7. Start dev mode with npm run start:dev or npm run start:vite.
8. If desktop startup fails, inspect scripts/launch.js, Electron logs, HANA_HOME, and ELECTRON_RUN_AS_NODE.
9. If server fails, run npm run server and inspect server/index.ts startup errors.
10. If packaging is needed, choose the platform script: dist, dist:win, or dist:linux.
11. Do not edit user data directories without confirmation.
12. Record every change and every command run.
```

## Safe prompt for Claude Code or Codex

```text
You are helping me deploy OpenHanako / HanaAgent for GitLearnOS.

Do not treat Claude Code/Codex as the daily GitLearnOS tutor. Your job is only to inspect, install, run, debug, or customize OpenHanako.

First read package.json, scripts/launch.js, scripts/dev-env.js, server/index.ts, core/agent.ts, lib/tools/subagent-tool.ts, and lib/tools/channel-tool.ts.

Confirm my OS, CPU architecture, Node version, npm version, and repository path.

Use the repository scripts rather than raw Electron commands:
- npm run start:dev
- npm run start:vite
- npm run server
- npm run typecheck
- npm test
- npm run dist:win / dist / dist:linux only if packaging is requested

If Electron fails to start, check whether ELECTRON_RUN_AS_NODE is interfering and use scripts/launch.js.

Do not delete ~/.hanako, ~/.hanako-dev, or user data without asking.

After OpenHanako runs, help me configure GitLearnOS inside OpenHanako using Maintainer, Source & Model Extractor, Practice & Review Coach, and optional Critic agents.

Report every command, file changed, error, and fix.
```

## What not to do

Do not turn this into a Claude Code or Codex learning workflow.

Do not maintain separate Claude/Codex-specific GitLearnOS setup docs here.

Do not write user learning data into the OpenHanako source repository.

Do not patch OpenHanako source unless the user explicitly asks for customization or bug fixing.

## After deployment

Once OpenHanako runs, switch from deployment mode to OpenHanako runtime mode:

```text
OpenHanako agent setup
→ create GitLearnOS Maintainer
→ create Source & Model Extractor
→ create Practice & Review Coach
→ optional Critic
→ connect target GitHub repository as learning state
→ keep original materials in local folders or desk files
```

For the OpenHanako agent configuration, see `docs/platform-agent-configuration.md`.
