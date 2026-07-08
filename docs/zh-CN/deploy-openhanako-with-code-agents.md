# 用 Claude Code 或 Codex 部署 OpenHanako

本教程说明 Claude Code、Codex、Cursor 或其他代码 Agent 在 GitLearnOS 生态里的正确角色。

它们不是本仓库维护的日常 GitLearnOS 学习运行层。

它们适合做一件事：

```text
部署、阅读、调试和定制 OpenHanako / HanaAgent
```

OpenHanako 跑起来以后，GitLearnOS 的桌面端工作流应该回到 OpenHanako 自己的 Agent、subagent、channel、desk、memory、Skills 和定时任务能力里运行。

## 边界

```text
ChatGPT
→ 日常 GitLearnOS 学习平台

OpenHanako / HanaAgent
→ 桌面端多 Agent、本地文件和更深入自动化运行时

Claude Code / Codex / Cursor / CLI agents
→ OpenHanako 的部署和源码辅助工具，不是本仓维护的日常学习层
```

除非用户明确偏好开发者工作流，不要把 Claude Code 或 Codex 变成 GitLearnOS 辅导平台。

应该用它们来阅读 OpenHanako 源码、安装依赖、运行脚本、诊断构建错误，并准备本地 OpenHanako 环境。

## OpenHanako 源码显示了什么

OpenHanako 是 Electron + React + Vite + Node 应用。

根目录 `package.json` 显示：

```text
name: hanako
main: desktop/bootstrap.cjs
bin: hana → cli/entry.ts
Node engine: >=24.12.0 <25
```

重要脚本包括：

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

项目通过 `package.json` 里的脚本构建 renderer、preload、theme、main、server、computer-use helper 和平台安装包。

## 源码层部署事实

### Node 版本很重要

OpenHanako 项目级要求 Node `>=24.12.0 <25`。

server 分发构建还会固定一个内置 Node runtime，目前是 `v24.15.0`，并在打包前校验 runtime checksum。

部署 Agent 应该先检查 Node：

```bash
node -v
npm -v
```

如果 Node 版本不对，先修 Node，不要一上来改应用源码。

### 开发启动器很重要

OpenHanako 使用 `scripts/launch.js` 作为跨平台启动器，处理 Electron、dev Electron、CLI 和 server 模式。

这个启动器会在启动 Electron 前清理 `ELECTRON_RUN_AS_NODE`，因为 VS Code 或 Claude Code 终端可能设置这个变量，导致 Electron 以纯 Node 模式启动失败。

所以 Claude Code 可以帮助部署，但部署时应该优先使用仓库脚本，而不是手写原始 Electron 命令。

### 开发数据目录

`scripts/dev-env.js` 会把开发数据放到：

```text
~/.hanako-dev
```

OpenHanako README 也说明生产默认数据目录是 `~/.hanako`，开发默认是 `~/.hanako-dev`。

部署 Agent 不要未经确认删除这些目录。

### Server 架构

OpenHanako server 是 Hono HTTP + WebSocket API，可以独立运行，也可以被 Electron 桌面应用 fork 启动。

它注册了 chat、sessions、models、agents、desk、skills、channels、DM、filesystem、preferences、bridge、commands、resources、mobile workbench、media 等路由。

对 GitLearnOS 来说，这说明 OpenHanako 不只是聊天界面，而是带文件、Agent、频道、书桌、技能和自动化表面的本地 Agent server。

## 给代码 Agent 的部署清单

Claude Code / Codex 部署 Agent 应该按这个顺序执行：

```text
1. Clone 或打开 liliMozi/openhanako。
2. 确认操作系统和 CPU 架构。
3. 确认 Node 版本是 >=24.12.0 且 <25。
4. 运行 npm install。
5. 运行 npm run typecheck。
6. 时间允许时运行 npm test。
7. 用 npm run start:dev 或 npm run start:vite 启动开发模式。
8. 如果桌面端启动失败，检查 scripts/launch.js、Electron 日志、HANA_HOME 和 ELECTRON_RUN_AS_NODE。
9. 如果 server 失败，运行 npm run server，并检查 server/index.ts 启动错误。
10. 如需打包，再选择 dist、dist:win 或 dist:linux。
11. 不经确认不要编辑或删除用户数据目录。
12. 记录每个命令、改动和错误。
```

## 给 Claude Code 或 Codex 的安全提示词

```text
你正在帮我部署 OpenHanako / HanaAgent，用于 GitLearnOS。

不要把 Claude Code / Codex 当成日常 GitLearnOS 辅导平台。你的任务只是阅读、安装、运行、调试或定制 OpenHanako。

先读 package.json、scripts/launch.js、scripts/dev-env.js、server/index.ts、core/agent.ts、lib/tools/subagent-tool.ts 和 lib/tools/channel-tool.ts。

确认我的操作系统、CPU 架构、Node 版本、npm 版本和仓库路径。

优先使用仓库脚本，不要手写原始 Electron 命令：
- npm run start:dev
- npm run start:vite
- npm run server
- npm run typecheck
- npm test
- 只有我要求打包时才运行 npm run dist:win / dist / dist:linux

如果 Electron 无法启动，检查 ELECTRON_RUN_AS_NODE 是否干扰，并使用 scripts/launch.js。

不要未经确认删除 ~/.hanako、~/.hanako-dev 或用户数据。

OpenHanako 跑起来后，帮我在 OpenHanako 里配置 GitLearnOS：Maintainer、Source & Model Extractor、Practice & Review Coach，以及可选 Critic agents。

汇报每个命令、文件改动、错误和修复。
```

## 不要做什么

不要把这件事变成 Claude Code 或 Codex 的学习工作流。

不要在本仓维护单独的 Claude / Codex 版 GitLearnOS 详细配置。

不要把用户学习数据写进 OpenHanako 源码仓库。

除非用户明确要求定制或修 bug，不要修改 OpenHanako 源码。

## 部署完成后

OpenHanako 能运行以后，从部署模式切到 OpenHanako 运行模式：

```text
OpenHanako Agent 设置
→ 创建 GitLearnOS Maintainer
→ 创建 Source & Model Extractor
→ 创建 Practice & Review Coach
→ 可选 Critic
→ 连接目标 GitHub 仓库作为学习状态
→ 原始材料保留在本地文件夹或书桌文件中
```

OpenHanako Agent 配置见 `docs/zh-CN/platform-agent-configuration.md`。
