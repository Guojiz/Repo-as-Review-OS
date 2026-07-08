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
ChatGPT / Claude
→ native daily GitLearnOS learning platform

OpenHanako / HanaAgent
→ desktop multi-agent runtime for local files and deeper automation

Claude Code / Codex / Cursor / CLI agents
→ deployment and source-code assistant for OpenHanako, not the maintained daily learning layer
```

Do not ask Claude Code or Codex to become the GitLearnOS tutoring platform unless the user intentionally wants a developer workflow.

Use them to read OpenHanako source, install dependencies, run scripts, diagnose build errors, and prepare a local OpenHanako setup.

## Source verification rule

OpenHanako is an external upstream project. Its files, scripts, and Node requirements can change.

Before running anything, the code agent must inspect the current upstream source, especially:

```text
README.md
package.json
scripts/launch.js
scripts/dev-env.js
server/index.ts
core/agent.ts
lib/tools/subagent-tool.ts
lib/tools/channel-tool.ts
```

The values in this guide are routing hints, not permanent facts. If `package.json` disagrees with this guide, trust the current upstream `package.json` and report the difference.

## What to inspect first

A code agent should first confirm:

```text
project name
Node engine requirement
available npm scripts
main entry
CLI entry
server entry
launcher behavior
development data location
production data location
```

Do not scan the whole source tree first. Start with the route files above.

## Node version check

Check Node and npm before installation:

```bash
node -v
npm -v
```

Then compare the result with the current `package.json` `engines` field.

If the Node version is wrong, fix Node before debugging app code.

Do not hard-code a Node version from this GitLearnOS guide. Use the current OpenHanako source as truth.

## Development launcher check

If OpenHanako provides a launcher script such as `scripts/launch.js`, use the project scripts rather than raw Electron commands.

This prevents common Electron startup problems caused by environment variables such as `ELECTRON_RUN_AS_NODE`.

If desktop startup fails, inspect:

```text
scripts/launch.js
scripts/dev-env.js
Electron logs
HANA_HOME
ELECTRON_RUN_AS_NODE
```

Do not delete user data folders without asking.

## Server architecture check

If the source has a server entry such as `server/index.ts`, inspect it before debugging server startup.

If server startup fails, run the server script only if it exists in `package.json`, then inspect the error output.

## Deployment checklist for code agents

A Claude Code / Codex deployment agent should follow this order:

```text
1. Clone or open liliMozi/openhanako.
2. Confirm OS and CPU architecture.
3. Read README.md and package.json.
4. Confirm Node and npm versions.
5. Compare Node with package.json engines.
6. Run npm install.
7. Run npm run typecheck only if the script exists.
8. Run npm test only if the script exists and the user wants the extra check.
9. Start dev mode with a package.json start/dev script such as start:dev or start:vite, only if present.
10. If desktop startup fails, inspect the launcher, Electron logs, HANA_HOME, and ELECTRON_RUN_AS_NODE.
11. If server fails, run the package.json server script if present and inspect server/index.ts.
12. If packaging is requested, choose a package script that exists, such as dist, dist:win, or dist:linux.
13. Do not edit or delete user data directories without confirmation.
14. Record every command, changed file, error, and fix.
```

## Safe prompt for Claude Code or Codex

```text
You are helping me deploy OpenHanako / HanaAgent for GitLearnOS.

Do not treat Claude Code/Codex as the daily GitLearnOS tutor. Your job is only to inspect, install, run, debug, or customize OpenHanako.

First read README.md, package.json, scripts/launch.js, scripts/dev-env.js, server/index.ts, core/agent.ts, lib/tools/subagent-tool.ts, and lib/tools/channel-tool.ts if they exist.

Confirm my OS, CPU architecture, Node version, npm version, repository path, package.json engines, and available npm scripts.

Use the repository scripts declared in package.json. Do not invent scripts.

Common candidates may include:
- npm run start:dev
- npm run start:vite
- npm run server
- npm run typecheck
- npm test
- npm run dist:win / dist / dist:linux only if packaging is requested

Run each candidate only if it exists in package.json.

If Electron fails to start, check whether ELECTRON_RUN_AS_NODE is interfering and use the project launcher if one exists.

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
→ connect or choose one learning state layer
→ keep original materials in local folders or desk files
```

The state layer may be:

```text
GitHub target repository
local git repository
local git + Obsidian vault
```

For the OpenHanako agent configuration, see `docs/platform-agent-configuration.md`.
