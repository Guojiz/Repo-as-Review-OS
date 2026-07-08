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
ChatGPT / Claude
→ 原生日常 GitLearnOS 学习平台

OpenHanako / HanaAgent
→ 桌面端多 Agent、本地文件和更深入自动化运行时

Claude Code / Codex / Cursor / CLI agents
→ OpenHanako 的部署和源码辅助工具，不是本仓维护的日常学习层
```

除非用户明确偏好开发者工作流，不要把 Claude Code 或 Codex 变成 GitLearnOS 辅导平台。

应该用它们来阅读 OpenHanako 源码、安装依赖、运行脚本、诊断构建错误，并准备本地 OpenHanako 环境。

## 源码核验规则

OpenHanako 是外部上游项目。它的文件、脚本和 Node 要求可能变化。

运行任何命令前，代码 Agent 必须先检查当前上游源码，尤其是：

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

本指南里的值是路线提示，不是永久事实。如果 `package.json` 和本指南不一致，以当前上游 `package.json` 为准，并汇报差异。

## 第一轮检查什么

代码 Agent 应该先确认：

```text
项目名
Node engine 要求
可用 npm scripts
main entry
CLI entry
server entry
launcher 行为
开发数据目录
生产数据目录
```

不要第一轮就扫描整个源码树。先按上面的路线文件检查。

## Node 版本检查

安装前先检查 Node 和 npm：

```bash
node -v
npm -v
```

然后和当前 `package.json` 的 `engines` 字段对比。

如果 Node 版本不对，先修 Node，不要一上来改应用源码。

不要从本 GitLearnOS 指南里硬编码 Node 版本。以当前 OpenHanako 源码为准。

## 开发启动器检查

如果 OpenHanako 提供 `scripts/launch.js` 这样的启动器，优先使用项目脚本，而不是手写原始 Electron 命令。

这可以避免 `ELECTRON_RUN_AS_NODE` 等环境变量导致 Electron 启动异常。

桌面端启动失败时检查：

```text
scripts/launch.js
scripts/dev-env.js
Electron logs
HANA_HOME
ELECTRON_RUN_AS_NODE
```

不要未经确认删除用户数据目录。

## Server 检查

如果源码里有 `server/index.ts` 这样的 server 入口，调试 server 启动前先检查它。

server 启动失败时，只有在 `package.json` 里存在 server 脚本时才运行，并检查错误输出。

## 给代码 Agent 的部署清单

Claude Code / Codex 部署 Agent 应该按这个顺序执行：

```text
1. Clone 或打开 liliMozi/openhanako。
2. 确认操作系统和 CPU 架构。
3. 读取 README.md 和 package.json。
4. 确认 Node 和 npm 版本。
5. 对比 Node 和 package.json engines。
6. 运行 npm install。
7. 只有 typecheck 脚本存在时，才运行 npm run typecheck。
8. 只有 test 脚本存在且用户需要额外检查时，才运行 npm test。
9. 只有 package.json 里存在 start:dev、start:vite 或其他启动脚本时，才启动开发模式。
10. 如果桌面端启动失败，检查启动器、Electron 日志、HANA_HOME 和 ELECTRON_RUN_AS_NODE。
11. 如果 server 失败，只有 server 脚本存在时才运行，并检查 server/index.ts。
12. 如需打包，只选择 package.json 中真实存在的脚本，例如 dist、dist:win 或 dist:linux。
13. 不经确认不要编辑或删除用户数据目录。
14. 记录每个命令、改动和错误。
```

## 给 Claude Code 或 Codex 的安全提示词

```text
你正在帮我部署 OpenHanako / HanaAgent，用于 GitLearnOS。

不要把 Claude Code / Codex 当成日常 GitLearnOS 辅导平台。你的任务只是阅读、安装、运行、调试或定制 OpenHanako。

先读 README.md、package.json、scripts/launch.js、scripts/dev-env.js、server/index.ts、core/agent.ts、lib/tools/subagent-tool.ts 和 lib/tools/channel-tool.ts；如果某个文件不存在，明确说明。

确认我的操作系统、CPU 架构、Node 版本、npm 版本、仓库路径、package.json engines 和可用 npm scripts。

优先使用 package.json 里声明的仓库脚本，不要发明脚本。

常见候选脚本可能包括：
- npm run start:dev
- npm run start:vite
- npm run server
- npm run typecheck
- npm test
- 只有我要求打包时才运行 npm run dist:win / dist / dist:linux

每个候选脚本只有在 package.json 里存在时才运行。

如果 Electron 无法启动，检查 ELECTRON_RUN_AS_NODE 是否干扰，并使用项目启动器。

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
→ 连接或选择一个学习状态层
→ 原始材料保留在本地文件夹或书桌文件中
```

状态层可以是：

```text
GitHub 目标仓库
本地 git 仓库
本地 git + Obsidian vault
```

OpenHanako Agent 配置见 `docs/zh-CN/platform-agent-configuration.md`。
