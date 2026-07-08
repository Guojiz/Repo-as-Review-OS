# 平台 Agent 配置教程

本指南给 GitLearnOS 可使用的平台族提供 AI 可执行配置规则。

它不能改变产品原则：

```text
GitLearnOS 核心
→ 一个活跃学习运行层
→ 一个学习状态层
→ 来源记录、模型、知识缺口、复习、dashboard
```

平台指南只是适配层，不是新的产品身份。

## 平台角色

```text
ChatGPT
→ 原生日常学习运行层
→ 默认最适合 GitHub 目标仓库

Claude
→ 原生日常学习运行层
→ 适合项目式阅读、写作、Artifacts 和长上下文

OpenHanako / HanaAgent
→ 可选桌面增强运行时
→ 适合本地文件、书桌、Skills、频道、定时任务和有限多 Agent 工作

Claude Code / Codex / Cursor / CLI agents
→ OpenHanako 的部署和源码辅助工具
→ 不是本仓维护的日常学习层
```

不要把 Claude 和 Claude Code 混在一起。

```text
Claude
→ 原生 AI 平台，用于学习对话、Projects、Artifacts、长上下文和写作

Claude Code
→ 代码 Agent，用于部署、阅读、调试或定制 OpenHanako
```

## 运行前自检

任何 AI 工具开始前必须汇报：

```text
运行环境：
状态层：
读取权限：
写入权限：
本地文件访问：
仓库访问：
记忆 / 项目指令：
桌面自动化：
需要用户手动完成的步骤：
```

没有实际能力时，不要声称已经编辑仓库、读取本地文件、完成定时任务或拥有长期记忆。

## 状态层边界

ChatGPT 和 Claude 默认优先 GitHub。

```text
原生平台默认
→ GitHub 目标仓库

原生平台本地路径
→ 只有运行时真的有本地文件访问权限才可直接写
→ 否则只能给出手动文件内容或补丁

OpenHanako 桌面路径
→ 用户授权文件访问后，本地 git 或本地 git + Obsidian 可以是真正状态层
```

## 共同 GitLearnOS 闭环

所有支持平台都遵守同一个闭环：

```text
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习
```

闭环比平台品牌重要。

## ChatGPT 原生配置

适合想要顺滑网页 / 手机日常学习和持续个性化的学习者。

最小配置：

```text
活跃运行层：ChatGPT
状态层：GitHub 目标仓库，除非运行时证明可以写本地
记忆：稳定偏好缓存
learner-profile.md：可检查学习画像
```

核心指令：

```text
你正在帮我在 ChatGPT 中运行 GitLearnOS。

使用我选定的状态层作为事实源。优先使用 GitHub 目标仓库。ChatGPT 记忆是主动偏好缓存，不是正式学习仓库。

行动前先判断你的运行环境、记忆、文件访问、仓库访问和权限边界。

遵守这个闭环：
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习。

不要编造缺失来源。除非你能说出具体改了哪些文件，否则不要声称已经编辑文件或仓库。
```

## Claude 原生配置

适合项目式组织、长上下文阅读、写作、Artifacts 和细致修改。

最小配置：

```text
活跃运行层：Claude
状态层：GitHub 目标仓库，除非运行时证明可以写本地
Claude Project：工作表面
Artifacts：草稿、可视化解释、小练习或临时教学材料
learner-profile.md：可检查学习画像
```

核心指令：

```text
你正在帮我在 Claude 中运行 GitLearnOS。

使用我选定的状态层作为事实源。除非我明确选择本地优先工作流且你确实有本地文件访问权限，否则优先使用 GitHub 目标仓库。Claude project context、artifacts 和 memory 都是工作表面，不是正式状态。

行动前先判断你的运行环境、memory/project 能力、文件访问、仓库访问和权限边界。

遵守这个闭环：
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习。

不要编造缺失来源。除非你能说出具体改了哪些文件，否则不要声称已经编辑文件或仓库。

Artifacts 可以用于草稿、可视化解释、表格、小应用或临时教学材料。重要学习状态必须写回 learner-profile.md、sources/、models/、knowledge-gaps/、reviews/ 或 dashboard.md。
```

## OpenHanako / HanaAgent 桌面配置

只有当学习者需要真正的桌面端运行时，才使用 OpenHanako。

适合它的原因：

- 本地来源材料；
- 本地文件读写；
- Agent 书桌；
- Skills；
- 定时任务；
- bridge channels；
- 浏览器和电脑操作；
- 一个活跃桌面运行时内部的有限多 Agent 委派。

不要把 OpenHanako 写成 GitLearnOS 的基础必需项。除非有明确接手，不要让它和 ChatGPT / Claude 并行写同一份状态层。

## OpenHanako 源码事实

这里的 OpenHanako / HanaAgent 说明基于 `liliMozi/openhanako` 真实源码，不是看名字猜的。

当前已核对事实：

```text
package.json
→ name: hanako
→ productName: HanaAgent
→ main: desktop/bootstrap.cjs
→ bin: hana → cli/entry.ts
→ node: >=24.12.0 <25

scripts/launch.js
→ 跨平台启动器
→ 启动 Electron 前清除 ELECTRON_RUN_AS_NODE

scripts/dev-env.js
→ 开发环境 HANA_HOME = ~/.hanako-dev

server/index.ts
→ Hono HTTP + WebSocket server
→ 路由包括 chat、sessions、models、agents、desk、skills、channels、filesystem、preferences、bridge、commands、resources、mobile workbench、media

core/agent.ts
→ Agent 拥有身份、人格、记忆、工具和 prompt 拼装逻辑

lib/tools/subagent-tool.ts
→ 支持 subagent 委派
→ 可选 agent target
→ 可选 model override
```

如果上游源码变了，先更新本指南，再改 GitLearnOS 部署说明。

## DeepTutor 对 OpenHanako 多 Agent 的参考

配置 OpenHanako Agent 前，先读 [DeepTutor 多 Agent 参考](zh-CN/deeptutor-multi-agent-reference.md)。

有价值的 DeepTutor 模式是：

```text
主 tutor loop
→ 需要时咨询或分派一个聚焦 Agent
→ 回到主 loop
→ 主 loop 回答并写入状态
```

不要复制 DeepTutor 完整平台。只借鉴受控 pipeline、咨询预算边界和学习状态反馈闭环。

## 推荐 OpenHanako Agent 布局

在 OpenHanako 内部，可以使用多个 Agent，但它们只是同一个活跃桌面运行时里的角色。

### 最小默认配置

```text
1. GitLearnOS Maintainer
   → 主 tutor loop
   → 负责 dashboard、learner-profile.md、索引、接手记录和最终写入

2. Source & Model Extractor
   → 在需要处理来源材料、错题、论文、截图或本地摘录时被咨询
   → 提出来源记录、可复用模型和知识缺口

3. Practice & Review Coach
   → 在需要复习题单、小测、间隔复习或下一步行动时被咨询
   → 提出练习和复习更新

4. Validator / Critic
   → 可选
   → 检查无来源断言、过期缺口、弱题目、答案正确性和学习画像漂移
```

Maintainer 是最终写入者。其他 Agent 只检查、提取、提出建议、出题或验证，避免多 Agent 漂移。

### DeepTutor-inspired 扩展配置

只有用户明确想要更重的 OpenHanako 配置时才使用：

```text
Maintainer / Orchestrator
→ 主 loop、状态边界、最终回答、最终写入

Personalized Investigator
→ 将用户任务映射到来源记录、当前缺口、学习画像和计划

Step Solver / Model Extractor
→ 执行计划，提取可复用模型，记录观察

Evidence Writer
→ 把结果写成面向学习者的解释或仓库笔记

Practice Idea Agent
→ 根据活跃缺口和来源上下文提出练习想法

Question Generator
→ 生成 question-answer-explanation 三元组

Validator / Critic
→ 独立检查正确性、来源 grounding、匹配度和难度

Memory Updaters
→ 更新 Session History、Weakness Diagnosis 和 Self-Reflection
```

扩展配置是选项，不是 GitLearnOS 默认要求。

## OpenHanako 状态层

桌面端可以不用 GitHub，但 GitHub 仍然有用。

三选一：

```text
本地 git + Obsidian
本地 git 仓库
GitHub 仓库
```

本地文件夹保存原始材料。状态层保存可检查学习状态。

权限要收窄：

```text
读取本地来源文件夹
只写 GitLearnOS 状态层或受控工作区
删除文件前先问
上传私人材料前先问
发布真实学习记录前先问
```

## 代码 Agent 部署助手

Claude Code、Codex、Cursor 和类似工具可以帮助部署 OpenHanako 本身。

适合做：

```text
源码检查
Node 版本检查
依赖安装
Electron 启动调试
server 调试
构建或打包问题排查
```

不要把它们当成本仓维护的日常 GitLearnOS 辅导层。

## 最终选择规则

```text
原生日常学习对话
→ ChatGPT 或 Claude

桌面本地文件 / 多 Agent 工作流
→ OpenHanako / HanaAgent

部署或调试 OpenHanako 源码
→ Claude Code / Codex / Cursor / CLI code agent

长期学习状态
→ 默认 GitHub 目标仓库
→ 只有活跃运行层真的能访问时，才用本地 git / Obsidian

原始来源材料
→ 本地文件夹，除非需要小摘录
```
