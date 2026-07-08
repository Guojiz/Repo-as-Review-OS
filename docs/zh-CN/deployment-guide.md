# 部署指南

这是 GitLearnOS 的 AI 专用、文件地址优先部署指南。

目标是轻量化部署。轻量化不是少写，而是让 AI 清楚知道：应该读哪些文件、创建哪些文件、更新哪些文件、不要碰哪些文件。

不要默认让 AI 吞完整个仓库。给它一张路线图。

## 核心想法

```text
少读文件
+ 精确状态层
+ 精确写入目标
+ 单一活跃运行层
= 更低 token 消耗，更少跑偏
```

## 不可改变的原则

1. 区分模板仓库和学习者自己的状态层。
2. 同一时间只使用一个活跃学习运行层。
3. 不要让 ChatGPT、Claude、OpenHanako、Codex、Cursor 或 Claude Code 同时更新同一个状态层。
4. 代码 Agent 只是部署或调试助手，不是日常学习导师。
5. 如果学习者已经提供学习目标，直接使用；如果没有，再问目标，然后再创建详细学习内容。
6. 除非运行环境确实具备能力，否则不要声称已经修改仓库、读取本地文件、更新记忆、完成定时任务或部署 OpenHanako。
7. 汇报每个读取、创建、修改或明确未触碰的文件。

## 仓库角色

```text
模板仓库
→ Guojiz/Repo-as-Review-OS
→ 方法、文档、示例、skills、公开说明

学习状态层
→ 用户自己的目标位置
→ 真实目标、学习画像、来源、模型、知识缺口、复习、dashboard、接手记录
```

不要把个人学习数据写进模板仓库。

学习状态层可以是：

```text
GitHub 目标仓库
本地 git 仓库
本地 git + Obsidian vault
```

GitHub 适合云同步和跨设备。本地 git + Obsidian 对 OpenHanako 桌面端可能已经够用。

## 模板仓库地址

```text
Repository:
https://github.com/Guojiz/Repo-as-Review-OS

Repository full name:
Guojiz/Repo-as-Review-OS
```

## 第一轮读取路线

中文部署第一轮只读：

```text
README.zh-CN.md
START-HERE.zh-CN.md
QUICKSTART.zh-CN.md
docs/zh-CN/deployment-guide.md
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/skill-and-memory-runtime.md
docs/zh-CN/single-runtime-rule.md
AGENTS.zh-CN.md
```

英文部署第一轮只读：

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

第一次部署不要读 `examples/`、`website/`、全部 `docs/` 或全部 `skills/`，除非用户明确要求。

## 按平台读取

### ChatGPT 原生平台

读：

```text
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-runtime-rule.md
```

只有学习者选择 ChatGPT 作为本次活跃运行层时，才使用 ChatGPT 路线。

### Claude 原生平台

读：

```text
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-runtime-rule.md
```

Claude 指 Claude 原生聊天 / 项目平台，不是 Claude Code。

### OpenHanako 桌面端

读：

```text
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-runtime-rule.md
docs/zh-CN/deploy-openhanako-with-code-agents.md
```

如果学习者想使用本地文件、desk files、Skills、记忆、选定定时任务、渠道或多 Agent 工作流，才选择 OpenHanako。

### Claude Code / Codex / Cursor 部署助手

只读部署文件：

```text
docs/zh-CN/deploy-openhanako-with-code-agents.md
```

Claude Code、Codex、Cursor 等工具不做日常学习层，只在用户明确选择 OpenHanako 路线时，用来部署、检查、调试或定制 OpenHanako。

## 最小目标状态树

在用户选定的学习状态层创建这些文件：

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
agents/handoff-notes/index.md
agents/handoff-notes/latest.md
automations/README.md
automations/organizer-critic/index.md
automations/practice-generator/index.md
archive/README.md
```

同时创建这些目录，即使第一轮只放 index：

```text
goals/
sources/
models/
knowledge-gaps/
reviews/
templates/
agents/
agents/handoff-notes/
automations/
automations/organizer-critic/
automations/practice-generator/
archive/
```

第一次部署不要创建额外目录。

## 必要目标文件

### `dashboard.md`

用途：学习状态首页。

必须包含：

```text
当前目标
当前主题
下一步行动
到期复习
活跃知识缺口
最后更新
接手记录链接
```

### `learner-profile.md`

用途：可检查的学习者记忆。

必须包含：

```text
稳定目标
偏好的解释方式
当前主题
活跃知识缺口摘要
重复错误模式
已解决缺口
记忆冲突说明
最后更新
```

### `GITLEARNOS.md`

用途：目标状态层的本地运行规则。

必须包含：

```text
单一活跃运行层规则
状态层位置
当前活跃平台
写入边界
接手规则
来源诚实规则
```

### Index 文件

为这些位置创建短索引文件：

```text
goals/goal-index.md
sources/source-index.md
models/model-index.md
knowledge-gaps/gap-index.md
reviews/review-index.md
reviews/due.md
agents/handoff-notes/index.md
automations/README.md
archive/README.md
```

索引文件应该短、以链接为主，方便 AI 快速扫描。

## 首次部署内容模板

### `dashboard.md`

```markdown
# Dashboard

## Active goal

- Goal: TBD
- Stage: setup
- Last updated: YYYY-MM-DD

## Next action

- 如果学习者已经提供学习目标，使用它填写 `goals/main-goal.md`。
- 如果没有，再询问第一个学习目标。

## Active knowledge gaps

- None recorded yet.

## Due reviews

- None yet.

## Handoff

- Latest handoff: agents/handoff-notes/latest.md
```

### `learner-profile.md`

```markdown
# Learner Profile

## Stable goal

TBD

## Preferred explanation style

TBD

## Current subjects

TBD

## Active knowledge gaps summary

None recorded yet.

## Recurring mistake patterns

None recorded yet.

## Resolved gaps

None recorded yet.

## Memory conflict notes

None.

## Last updated

YYYY-MM-DD
```

### `GITLEARNOS.md`

```markdown
# GitLearnOS Local Rules

## Active runtime

TBD: ChatGPT / Claude / OpenHanako

## State layer

This folder is the learning state layer.

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

### `agents/handoff-notes/latest.md`

```markdown
# Latest Handoff

## Active platform leaving

TBD

## New platform entering

TBD

## Current goal

TBD

## Last files updated

- None yet.

## Active gaps

- None yet.

## Next action

如果学习者已经提供学习目标，直接使用；如果没有，再询问第一个学习目标。
```

## 从模板仓库复制的最小集合

个人学习状态层只复制或重建这些文件：

```text
GITLEARNOS.md
learner-profile.md
dashboard.md
goals/main-goal.md
sources/source-index.md
models/model-index.md
knowledge-gaps/gap-index.md
reviews/review-index.md
reviews/due.md
agents/handoff-notes/latest.md
```

不要复制全部公开 demo、全部文档、网站文件或 issue 模板。

## 精确部署提示词

### ChatGPT 部署提示词

```text
你正在帮我在 ChatGPT 中部署 GitLearnOS。

模板仓库：
https://github.com/Guojiz/Repo-as-Review-OS

先只读这些模板文件：
- README.zh-CN.md
- START-HERE.zh-CN.md
- QUICKSTART.zh-CN.md
- docs/zh-CN/deployment-guide.md
- docs/zh-CN/native-ai-platform-deployment.md
- docs/zh-CN/platform-agent-configuration.md
- docs/zh-CN/single-runtime-rule.md

我的状态层是：
<粘贴 GitHub 仓库、本地 git 文件夹或 Obsidian vault 路径>

创建或检查这些文件：
- dashboard.md
- learner-profile.md
- GITLEARNOS.md
- goals/main-goal.md
- sources/source-index.md
- models/model-index.md
- knowledge-gaps/gap-index.md
- reviews/review-index.md
- reviews/due.md
- agents/handoff-notes/latest.md

不要读取整个仓库，除非我要求。
不要创建额外目录，除非必要。
除非你能说出具体改了哪些文件，否则不要声称已经编辑。
如果我已经给出学习目标，直接使用；如果没有，再问我的第一个学习目标，然后再创建详细学习内容。
```

### Claude 部署提示词

```text
你正在帮我在 Claude 中部署 GitLearnOS。

模板仓库：
https://github.com/Guojiz/Repo-as-Review-OS

先只读这些模板文件：
- README.zh-CN.md
- START-HERE.zh-CN.md
- QUICKSTART.zh-CN.md
- docs/zh-CN/deployment-guide.md
- docs/zh-CN/native-ai-platform-deployment.md
- docs/zh-CN/platform-agent-configuration.md
- docs/zh-CN/single-runtime-rule.md

我的状态层是：
<粘贴 GitHub 仓库、本地 git 文件夹或 Obsidian vault 路径>

把 Claude Project context、文件、memory 和 artifacts 都当作工作表面。
状态层才是事实源。

创建或检查这些文件：
- dashboard.md
- learner-profile.md
- GITLEARNOS.md
- goals/main-goal.md
- sources/source-index.md
- models/model-index.md
- knowledge-gaps/gap-index.md
- reviews/review-index.md
- reviews/due.md
- agents/handoff-notes/latest.md

Artifacts 只用于草稿、可视化解释或临时教学材料。
长期学习状态必须写回状态层。
如果我已经给出学习目标，直接使用；如果没有，再问我的第一个学习目标，然后再创建详细学习内容。
```

### OpenHanako 部署提示词

```text
你正在帮我在 OpenHanako / HanaAgent 中部署 GitLearnOS。

模板仓库：
https://github.com/Guojiz/Repo-as-Review-OS

先只读这些模板文件：
- README.zh-CN.md
- docs/zh-CN/platform-agent-configuration.md
- docs/zh-CN/single-runtime-rule.md
- docs/zh-CN/deployment-guide.md

我的来源文件夹是：
<粘贴本地来源文件夹路径>

我的状态层是：
<粘贴本地 git 文件夹、Obsidian vault 或 GitHub 仓库>

只创建三个 Agent：
1. GitLearnOS Maintainer
2. Source & Model Extractor
3. Practice & Review Coach

Critic 只有我要求时再创建。

只开启必要功能：
- memory
- local file 或 desk access
- selected Skills

不要开启过宽文件权限。
不要开启不必要定时任务。
不要让多个平台同时更新同一个状态层。
如果我已经给出学习目标，直接使用；如果没有，再问我的第一个学习目标，然后再创建详细学习内容。
```

## OpenHanako 源码路线给代码 Agent

用 Claude Code、Codex、Cursor 或其他代码 Agent 部署 OpenHanako 时，第一轮只检查这些 OpenHanako 源码文件：

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

不要第一轮就扫描整个源码树。

第一次部署不要修改源码，除非构建失败且用户批准修复。

## OpenHanako 命令规则

不要假设脚本一定存在。先读取 `package.json`，再运行实际存在的脚本。

推荐顺序：

```bash
node -v
npm -v
npm install
npm run typecheck   # 只有存在时才运行
npm test            # 只有存在且有必要时才运行
npm run start:dev   # 只有存在时才运行
```

如果仓库使用不同启动脚本，使用 `package.json` 中声明的脚本，并汇报替换原因。

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

用户要求打包时，才运行 `package.json` 中实际存在的平台脚本，例如 `dist`、`dist:win` 或 `dist:linux`。

第一次部署不要默认打包。

## 切换平台检查清单

从 ChatGPT 切 Claude、Claude 切 ChatGPT、原生平台切 OpenHanako、OpenHanako 切原生平台之前：

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

## 省 token 规则

部署时遵守这些规则：

```text
先读路线文件。
再读平台专用文件。
先创建骨架，再读例子。
如果学习者已经给出目标，直接使用；如果没有，再询问第一个学习目标，然后再创建详细内容。
用户不要求 demo，就不读 examples。
不要打开所有 docs。
不要复制 website 文件。
不要安装所有 skills。
不要创建太多 agents。
```

## 部署后必须汇报

AI 必须汇报：

```text
Active runtime:
State layer:
Files read:
Files created:
Files changed:
Files not touched:
Manual steps needed:
Next action:
```

如果不能写文件，必须说：

```text
我在这个运行环境里不能写入状态层。下面是你需要手动创建的精确文件和内容。
```

## 部署完成标准

只有这些全部满足，才算部署完成：

```text
已选择一个活跃运行层
已选择一个状态层
已创建最小文件树
已创建 GITLEARNOS.md
已创建 learner-profile.md
已创建 dashboard.md
已创建接手记录
已使用或询问第一个学习目标
没有留下并行运行层
```

缺一个，都不算完成。
