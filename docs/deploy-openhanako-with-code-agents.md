# Deploy OpenHanako with Claude Code or Codex

This guide explains the role of Claude Code, Codex, Cursor, or another coding agent in the GitLearnOS ecosystem.

They are not the daily GitLearnOS learning runtime maintained by this repository.

They are useful for one job:

```text
deploy, inspect, debug, and customize OpenHanako / HanaAgent
```

After OpenHanako is running, the GitLearnOS desktop workflow should run inside OpenHanako through its native Agent, subagent, channel, desk, memory, Skills, and scheduled-task capabilities.

## Boundary

```text
ChatGPT / Claude
→ native daily GitLearnOS learning platforms

OpenHanako / HanaAgent
→ optional desktop runtime for local files and deeper automation

Claude Code / Codex / Cursor / CLI agents
→ OpenHanako deployment and source-code assistants
→ not the maintained daily learning layer
```

Do not ask Claude Code or Codex to become the GitLearnOS tutoring platform unless the user intentionally wants a developer workflow.

## Source facts to verify first

A code agent must inspect real OpenHanako files before giving confident deployment instructions.

Current verified files:

```text
Repository:
liliMozi/openhanako

README.md
package.json
scripts/launch.js
scripts/dev-env.js
server/index.ts
core/agent.ts
lib/tools/subagent-tool.ts
lib/tools/channel-tool.ts
scripts/build-server.mjs
```

Do not scan the whole source tree first. Do not patch source code during first deployment unless the build fails and the user approves a fix.

## What the OpenHanako source shows

The current source shows:

```text
package.json
→ name: hanako
→ productName: HanaAgent
→ main: desktop/bootstrap.cjs
→ bin: hana → cli/entry.ts
→ node engine: >=24.12.0 <25
```

Important scripts include:

```text
npm run start
npm run start:dev
npm run start:vite
npm run dev:renderer
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

Other source facts:

- `scripts/launch.js` is a cross-platform launcher and clears `ELECTRON_RUN_AS_NODE` before spawning Electron.
- `scripts/dev-env.js` sets development `HANA_HOME` to `~/.hanako-dev`.
- `scripts/build-server.mjs` currently pins bundled server Node runtime `v24.15.0` and verifies runtime checksums before packaging.
- `server/index.ts` is a Hono HTTP + WebSocket server and registers routes for chat, sessions, models, agents, desk, skills, channels, filesystem, preferences, bridge, commands, resources, mobile workbench, media, and more.
- `core/agent.ts` describes an Agent as having identity, personality, memory, tools, and prompt-building logic.
- `lib/tools/subagent-tool.ts` supports delegated subagents with optional `agent`, optional `model`, and read/write access tiers.

## Deployment checklist for code agents

Follow this order:

```text
1. Clone or open liliMozi/openhanako.
2. Confirm OS and CPU architecture.
3. Confirm Node version is >=24.12.0 and <25.
4. Run npm install.
5. Run npm run typecheck.
6. Run npm test if time allows.
7. Start normal dev desktop mode with npm run start:dev.
8. If using Vite live renderer mode, run npm run dev:renderer in one terminal and npm run start:vite in another.
9. If desktop startup fails, inspect scripts/launch.js, Electron logs, HANA_HOME, and ELECTRON_RUN_AS_NODE.
10. If server fails, run npm run server and inspect server/index.ts startup errors.
11. If packaging is needed, choose the platform script: dist, dist:win, or dist:linux.
12. Do not edit user data directories without confirmation.
13. Record every command, every changed file, every error, and every fix.
```

## Safe prompt for Claude Code or Codex

```text
You are helping me deploy OpenHanako / HanaAgent for GitLearnOS.

Do not treat Claude Code/Codex as the daily GitLearnOS tutor. Your job is only to inspect, install, run, debug, or customize OpenHanako.

First read package.json, scripts/launch.js, scripts/dev-env.js, server/index.ts, core/agent.ts, lib/tools/subagent-tool.ts, and lib/tools/channel-tool.ts.

Confirm my OS, CPU architecture, Node version, npm version, and repository path.

Use the repository scripts rather than raw Electron commands:
- npm run start:dev
- npm run dev:renderer + npm run start:vite only when live renderer mode is needed
- npm run server
- npm run typecheck
- npm test
- npm run dist:win / dist / dist:linux only if packaging is requested

If Electron fails to start, check whether ELECTRON_RUN_AS_NODE is interfering and use scripts/launch.js.

Do not delete ~/.hanako, ~/.hanako-dev, or user data without asking.

After OpenHanako runs, help me configure GitLearnOS inside OpenHanako using Maintainer, Source & Model Extractor, Practice & Review Coach, and optional Critic agents. The Maintainer should be the final writer to the state layer.

Report every command, file changed, error, and fix.
```

## What not to do

- Do not turn this into a Claude Code or Codex learning workflow.
- Do not maintain separate Claude/Codex-specific GitLearnOS setup docs here.
- Do not write user learning data into the OpenHanako source repository.
- Do not patch OpenHanako source unless the user explicitly asks for customization or bug fixing.
- Do not invent OpenHanako file paths or agent IDs. Read the actual source or roster first.

## After deployment

Once OpenHanako runs, switch from deployment mode to OpenHanako runtime mode:

```text
OpenHanako agent setup
→ create GitLearnOS Maintainer
→ create Source & Model Extractor
→ create Practice & Review Coach
→ optional Critic only when needed
→ choose one state layer
→ keep original materials in local folders or desk files
```

For OpenHanako agent configuration, see `docs/platform-agent-configuration.md`.
