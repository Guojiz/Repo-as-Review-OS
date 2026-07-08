# 部署指南

这是 GitLearnOS 的文件地址优先部署指南。

目标是轻量化部署。

轻量化不是少写，而是让 AI 清楚知道：应该读哪些文件、创建哪些文件、更新哪些文件、不要碰哪些文件。

不要默认让 AI 吞完整个仓库。给它一张路线图。

## 核心想法

```text
少读文件
+ 精确路径
+ 精确状态层
+ 精确写入目标
= 更低 token 消耗，更少跑偏
```

好的 GitLearnOS 部署应该像一套小型手术工具，不像一次仓库观光旅行。

## 仓库角色

始终区分两个角色。

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

GitHub 适合云同步和跨设备。

本地 git + Obsidian 对 OpenHanako 桌面端可能已经够用。

## 模板仓库地址

```text
Repository:
https://github.com/Guojiz/Repo-as-Review-OS

Repository full name:
Guojiz/Repo-as-Review-OS
```

## 第一轮只读这些文件

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

## 第二轮按平台读文件

### ChatGPT 原生平台

读：

```text
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-runtime-rule.md
```

英文：

```text
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
```

### Claude 原生平台

读：

```text
docs/zh-CN/native-ai-platform-deployment.md
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-runtime-rule.md
```

英文：

```text
docs/native-ai-platform-deployment.md
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
```

Claude 指 Claude 原生平台，不是 Claude Code。

### OpenHanako 桌面端

读：

```text
docs/zh-CN/platform-agent-configuration.md
docs/zh-CN/single-runtime-rule.md
docs/zh-CN/deploy-openhanako-with-code-agents.md
```

英文：

```text
docs/platform-agent-configuration.md
docs/single-active-runtime-rule.md
docs/deploy-openhanako-with-code-agents.md
```

### Claude Code / Codex / Cursor 部署助手

只读部署文件：

```text
docs/zh-CN/deploy-openhanako-with-code-agents.md
```

英文：

```text
docs/deploy-openhanako-with-code-agents.md
```

Claude Code、Codex、Cursor 不做日常学习层，只用于部署或调试 OpenHanako。

## 精确目标状态树

在用户选定的学习状态层创建这些文件。

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

即使第一版只是 index，也要创建目录。

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

## 目标文件作用

### `dashboard.md`

用途：

```text
学习状态首页
```

必须包含：

```text
当前目标
当前科目
下一步行动
到期复习
活跃知识缺口
最后更新时间
接手记录链接
```

### `learner-profile.md`

用途：

```text
可检查的学习者记忆
```

必须包含：

```text
稳定目标
偏好解释方式
当前科目
活跃知识缺口摘要
反复错误模式
已解决缺口
记忆冲突记录
最后更新时间
```

### `GITLEARNOS.md`

用途：

```text
目标状态层的本地操作规则
```

必须包含：

```text
单一活跃运行层规则
状态层位置
活跃平台
写入边界
接手规则
来源诚实规则
```

### `goals/main-goal.md`

用途：

```text
主要学习目标
```

必须包含：

```text
目标陈述
为什么重要
时间范围
当前阶段
成功标准
关联来源
关联模型
关联知识缺口
复习频率
```

### `sources/source-index.md`

用途：

```text
来源记录索引
```

每个来源记录放在：

```text
sources/YYYY-MM-DD-short-title.md
```

来源状态只能是：

```text
complete
excerpt-only
local-only
missing
uncertain
```

### `models/model-index.md`

用途：

```text
可复用学习模型索引
```

每个模型卡放在：

```text
models/YYYY-MM-DD-short-model-name.md
```

模型不是摘要。模型必须捕捉可迁移模式。

### `knowledge-gaps/gap-index.md`

用途：

```text
活跃和已解决知识缺口索引
```

每个缺口记录放在：

```text
knowledge-gaps/YYYY-MM-DD-short-gap-name.md
```

知识缺口要说明学习者还不能识别、应用、解释或迁移什么。

### `reviews/review-index.md`

用途：

```text
复习题单和练习结果索引
```

每个复习题单放在：

```text
reviews/YYYY-MM-DD-review-topic.md
```

### `reviews/due.md`

用途：

```text
短小的到期复习列表
```

必须保持短。它应该链接到真实 review 文件。

### `agents/handoff-notes/latest.md`

用途：

```text
一页式平台接手记录
```

切换平台时使用。

## 首次部署内容模板

### `dashboard.md`

```markdown
# Dashboard

## Active goal

- Goal: TBD
- Stage: setup
- Last updated: YYYY-MM-DD

## Next action

- Ask the learner for the first learning goal.

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

Ask the learner for the first learning goal.
```

## 从模板仓库最小复制范围

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

不要复制所有公开 demo。

不要复制所有文档。

不要复制 website 文件。

不要复制 issue templates。

## 精确原生平台部署提示词

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
骨架准备好后，问我的第一个学习目标。
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
骨架准备好后，问我的第一个学习目标。
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
```

## 代码 Agent 研究 OpenHanako 的精确源码地址

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

用户要求打包时才运行平台脚本：

```bash
npm run dist:win
npm run dist:linux
npm run dist
```

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
先问第一个学习目标，再生成详细内容。
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
已询问第一个学习目标
没有留下并行运行层
```

缺一个，都不算完成。