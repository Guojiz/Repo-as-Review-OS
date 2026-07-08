# 部署指南

这是 GitLearnOS 的文件地址优先部署指南，写给 AI 看。

目标是轻量化部署：精确文件、精确状态层、精确写入边界，不假装拥有不存在的能力。

## 不可改变的原则

```text
一个学习者
→ 一个活跃学习运行层
→ 一个学习状态层
→ 一条接手路径
```

不要把 GitLearnOS 写成 ChatGPT、Claude、OpenHanako、Codex、Claude Code 同时写同一份学习状态的平台大杂烩。

## 仓库角色

```text
模板仓库
→ Guojiz/Repo-as-Review-OS
→ 公开方法、文档、示例、skill、规则

学习状态层
→ 用户自己选择的目标位置
→ 真实目标、学习画像、来源、模型、知识缺口、复习、dashboard、接手记录
```

不要把个人学习数据写进模板仓库。

## 状态层规则

默认优先使用 GitHub，尤其是 ChatGPT 和 Claude。

```text
推荐默认
→ GitHub 目标仓库

本地优先桌面替代
→ 本地 git 仓库
→ 本地 git + Obsidian vault
```

对 ChatGPT 或 Claude 来说，本地路径不是自动可写的。只有在运行环境真的有本地文件访问权限，或者 AI 只给出精确补丁让用户手动应用时，才可以把本地 git / Obsidian 当作状态层。

对 OpenHanako 来说，本地 git 或本地 git + Obsidian 可以是真正状态层，因为桌面运行时在用户授权后可以访问本地文件。

## 第一轮只读这些文件

英文路线：

```text
README.md
START-HERE.md
QUICKSTART.md
docs/deployment-guide.md
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/skill-and-memory-runtime.md
docs/single-active-runtime-rule.md
AGENTS.md
```

中文路线：

```text
README.zh-CN.md
START-HERE.zh-CN.md
QUICKSTART.zh-CN.md
docs/zh-CN/deployment-guide.md
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/skill-and-memory-runtime.md
docs/zh-CN/single-active-runtime-rule.md
AGENTS.zh-CN.md
```

第一次部署不要读全部 examples、全部 docs、website 或全部 skills，除非用户要求。

## 平台路线

### ChatGPT 原生平台

读：

```text
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-active-runtime-rule.md
```

ChatGPT 适合原生记忆优先的日常学习流程。默认状态层应是 GitHub 目标仓库。自动化 / scheduled prompts 如果没有实时仓库工具，只能作为接手提示，不能声称已完成仓库写入。

### Claude 原生平台

读：

```text
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-active-runtime-rule.md
```

Claude 指原生 Claude 平台，不是 Claude Code。Claude 适合项目 / artifact 优先的阅读、写作、草稿和长上下文工作。Artifacts 是工作表面，不是长期学习状态。

### OpenHanako 桌面运行时

读：

```text
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-active-runtime-rule.md
docs/zh-CN/deploy-openhanako-with-code-agents.md
```

OpenHanako / HanaAgent 是桌面增强运行时，适合本地文件、Agent 书桌、记忆、Skills、定时任务、频道和 subagent。它是可选路径，不是 GitLearnOS 基础部署必需项。

### Claude Code / Codex / Cursor

读：

```text
docs/zh-CN/deploy-openhanako-with-code-agents.md
```

这些工具只用于部署、阅读、调试或定制 OpenHanako。除非用户明确偏好开发者工作流，否则不要让它们成为日常 GitLearnOS 辅导层。

## 最小目标状态树

在选定学习状态层创建或检查：

```text
dashboard.md
learner-profile.md
GITLEARNOS.md
goals/main-goal.md
goals/goal-index.md
sources/source-index.md
models/model-index.md
knowledge-gaps/gap-index.md
reviews/review-index.md
reviews/due.md
templates/source-record-template.md
templates/model-card-template.md
templates/knowledge-gap-template.md
templates/review-card-template.md
agents/handoff-notes/latest.md
automations/README.md
archive/README.md
```

只创建这些文件需要的目录。首次部署不要创建额外子系统。

## 首次部署内容规则

未知字段可以写 `TBD`。如果用户已经给出学习目标，必须直接写入 `dashboard.md`、`learner-profile.md` 和 `goals/main-goal.md`。如果用户没有给学习目标，再问，不要编。

## 必须创建的本地规则文件

在学习状态层创建 `GITLEARNOS.md`：

```markdown
# GitLearnOS Local Rules

## Active runtime

TBD: ChatGPT / Claude / OpenHanako

## State layer

This folder or repository is the learning state layer.

## Rule

Use one active learning runtime at a time.

## Write boundary

Write learning state only inside this state layer.

Do not write personal learning data into the template repository.

## Source honesty

Mark sources as complete, excerpt-only, local-only, missing, or uncertain.

## Handoff

Before switching platforms, update agents/handoff-notes/latest.md.
```

## 原生平台部署提示词

```text
你正在帮我部署 GitLearnOS。

模板仓库：
https://github.com/Guojiz/Repo-as-Review-OS

一次只使用一个活跃运行层。不要让 ChatGPT、Claude、OpenHanako、Codex 或 Claude Code 同时更新同一个学习状态层。

先只读部署路线文件。不要读取整个仓库，除非我要求。

我选择的活跃运行层是：
<ChatGPT / Claude / OpenHanako>

我的学习状态层是：
<粘贴 GitHub 仓库、本地 git 文件夹或 Obsidian vault 路径>

如果状态层是本地路径，而你没有本地文件访问权限，不要声称已经编辑。请给出我可以手动应用的精确文件内容或补丁。

创建或检查最小状态树。如果我已经给出学习目标，直接使用；如果没有，再问我，不要编。

最后汇报：活跃运行层、状态层、读过的文件、创建的文件、修改的文件、需要我手动完成的步骤和下一步行动。
```

## OpenHanako 源码事实

用代码 Agent 部署 OpenHanako 时，必须先按 `liliMozi/openhanako` 真实源码核对，不要凭感觉写教程。

当前已核对的事实：

- `package.json` 的 package name 是 `hanako`，productName 是 `HanaAgent`，main 是 `desktop/bootstrap.cjs`，CLI bin 是 `hana → cli/entry.ts`，Node engine 是 `>=24.12.0 <25`。
- `scripts/launch.js` 是跨平台启动器，并在启动 Electron 前清除 `ELECTRON_RUN_AS_NODE`。
- `scripts/dev-env.js` 把开发环境 `HANA_HOME` 设为 `~/.hanako-dev`。
- `server/index.ts` 是 Hono HTTP + WebSocket server，包含 chat、sessions、models、agents、desk、skills、channels、filesystem、preferences、bridge、commands、resources、mobile workbench、media 等路由。
- `core/agent.ts` 把 Agent 建模为拥有身份、人格、记忆、工具和 prompt 拼装逻辑的实例。
- `lib/tools/subagent-tool.ts` 支持带 `agent` 参数的任务委派，也有可选 `model` override；不要编造 Agent ID，应该先读取实际 roster。

## OpenHanako 命令顺序

按这个顺序运行：

```bash
node -v
npm -v
npm install
npm run typecheck
npm test
npm run start:dev
```

不要把 `npm run start:vite` 当成独立首次启动命令。只有在另一个终端同时运行 renderer dev server，例如 `npm run dev:renderer` 时，才使用它。

桌面端启动失败时检查：

```text
scripts/launch.js
scripts/dev-env.js
Electron logs
HANA_HOME
ELECTRON_RUN_AS_NODE
```

server 启动失败时检查：

```text
server/index.ts
npm run server output
```

首次部署不要修改 OpenHanako 源码，除非构建失败且用户明确批准修复。

## 平台切换检查清单

切换平台前：

```text
1. 更新 dashboard.md。
2. 更新 learner-profile.md。
3. 更新 knowledge-gaps/gap-index.md。
4. 更新 reviews/review-index.md。
5. 写 agents/handoff-notes/latest.md。
6. 停止旧运行层。
7. 新运行层从 latest.md 开始。
```

不要让两个平台同时更新同一个状态层。

## 部署成功定义

只有满足这些条件才算部署完成：

```text
已选择一个活跃运行层
已选择一个状态层
已创建最小文件树，或已给出精确手动补丁
已创建或给出 GITLEARNOS.md
已创建或给出 learner-profile.md
已创建或给出 dashboard.md
已创建或给出 handoff note
已使用或询问第一个学习目标
没有留下并行活跃运行层
```
