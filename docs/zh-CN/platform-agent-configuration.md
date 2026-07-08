# 平台 Agent 配置教程

本教程详细维护 GitLearnOS 的三个主要平台族：

```text
原生 AI 平台
→ ChatGPT
→ Claude

桌面端增强 Agent 运行时
→ OpenHanako / HanaAgent

代码 Agent 部署助手
→ Claude Code / Codex / Cursor
```

不要把 Claude 和 Claude Code 混在一起。

```text
Claude
→ 原生 AI 平台，用于学习对话、Projects、Artifacts、长上下文、写作和复习

Claude Code
→ 代码 Agent，用于部署、阅读、调试或定制 OpenHanako
```

ChatGPT 和 Claude 的原生平台部署见 `docs/zh-CN/native-ai-platform-deployment.md`。

用代码 Agent 部署 OpenHanako 见 `docs/zh-CN/deploy-openhanako-with-code-agents.md`。

本仓主动支持的平台应该遵守同一个 GitLearnOS 学习闭环：

```text
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习
```

## 运行前先自检

任何 AI 工具开始前都应该先汇报：

```text
运行环境：
原生记忆：
项目 / 工作区指令：
状态层：
仓库或本地 git 访问：
本地文件访问：
桌面自动化：
需要用户手动完成的步骤：
```

没有实际能力时，不要声称已经编辑仓库、读取本地文件、完成定时任务或拥有长期记忆。

## 推荐平台图

```text
ChatGPT
→ 本仓详细支持的原生日常学习平台
→ 记忆校准、推理、解释、写作、GitHub 辅助工作和轻量自动化接手

Claude
→ 本仓详细支持的原生日常学习平台
→ 项目式组织、长上下文阅读、写作、Artifacts、细致草稿和仓库辅助工作

OpenHanako / HanaAgent
→ 本仓详细支持的桌面端增强运行时
→ 本地文件、多 Agent、Skills、定时任务、便携入口、浏览器 / 电脑操作和更深入的文件自动化

Claude Code / Codex / Cursor / CLI agents
→ 只作为 OpenHanako 部署和源码辅助工具
→ 不是本仓维护的日常 GitLearnOS 辅导平台
```

ChatGPT 和 Claude 是两个原生平台代表。其他聊天式 AI 平台可以照着它们适配。

OpenHanako 是用户需要本机多 Agent 系统时的桌面端增强推荐。

## 原生平台部署

ChatGPT 和 Claude 使用：

```text
docs/zh-CN/native-ai-platform-deployment.md
```

简版：

```text
ChatGPT
→ 记忆优先的原生工作流

Claude
→ Project / Artifact 优先的原生工作流

GitHub / 本地 git / Obsidian
→ 长期学习状态
```

一次只使用一个活跃原生平台。不要让 ChatGPT 和 Claude 同时更新同一份 learner-profile、knowledge-gaps、reviews 或 dashboard。

## ChatGPT 原生配置

适合想要最顺滑手机 / 网页日常学习流程，以及较强持续个性化的学习者。

最小配置：

```text
状态层：GitHub、本地 git 或本地 git + Obsidian
活跃平台：ChatGPT
记忆：稳定偏好缓存
learner-profile.md：可检查学习画像
```

核心指令：

```text
你正在帮我在 ChatGPT 中运行 GitLearnOS。

使用我选定的状态层作为学习状态事实源。ChatGPT 记忆是主动偏好缓存，不是仓库本身。

行动前先识别你的运行环境、记忆、文件访问、仓库访问和权限边界。

遵守这个闭环：
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习。

不要编造缺失来源。除非你能说出具体改了哪些文件，否则不要声称已经编辑文件或仓库。
```

## Claude 原生配置

适合需要项目式组织、长上下文阅读、写作、Artifacts 和细致修改的学习者。

最小配置：

```text
状态层：GitHub、本地 git 或本地 git + Obsidian
活跃平台：Claude
Claude Project：工作表面
Artifacts：草稿、可视化解释、小练习或临时教学材料
learner-profile.md：可检查学习画像
```

核心指令：

```text
你正在帮我在 Claude 中运行 GitLearnOS。

使用我选定的状态层作为学习状态事实源。Claude project context、artifacts 和 memory 是工作表面，不是长期状态本身。

行动前先识别你的运行环境、记忆 / project 能力、文件访问、仓库访问和权限边界。

遵守这个闭环：
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习。

不要编造缺失来源。除非你能说出具体改了哪些文件，否则不要声称已经编辑文件或仓库。

Artifacts 可以用于草稿、可视化解释、表格、小应用或临时教学材料。重要学习状态必须写回 learner-profile.md、sources/、models/、knowledge-gaps/、reviews/ 或 dashboard.md。
```

## OpenHanako / HanaAgent 桌面端配置

当用户需要真正的桌面端 Agent 系统时使用 OpenHanako。

OpenHanako 比泛泛的桌面 Agent 更适合这些 GitLearnOS 场景：

- 本地来源材料；
- 文件读写；
- 浏览器和电脑操作；
- Skills；
- Agent 记忆；
- 定时任务；
- 多 Agent 协作；
- 本地桌面工作区和书桌文件；
- 从消息或社交平台进入的便携入口。

## 为什么 OpenHanako 适合 GitLearnOS

OpenHanako / HanaAgent 自己的说明里写了：它是有记忆、有性格、会主动行动，还能多个 Agent 在电脑上一同工作的 AI agent。

它的功能包括读写文件、命令、终端会话、浏览器、搜索、截图、网页检查、Skills、角色卡、多 Agent、书桌、定时任务、沙盒、插件、多平台桥接、移动 PWA 和 LAN 前端。

源码里每个 Agent 也被建模成拥有自己的身份、人格、记忆、工具和 prompt 拼装逻辑。

## 推荐 OpenHanako Agent 布局

创建三个 GitLearnOS Agent：

```text
1. GitLearnOS Maintainer / 维护者
   → 负责仓库结构、dashboard、learner-profile.md、索引和接手记录

2. Source & Model Extractor / 来源与模型提取器
   → 读取本地摘录或上传材料，创建来源记录，提取可复用模型，记录知识缺口

3. Practice & Review Coach / 练习与复习教练
   → 根据最近模型、活跃知识缺口、复习历史和间隔复习生成个性化题单
```

可选第四个 Agent：

```text
4. Critic / 批判者
   → 审查模糊笔记、无来源结论、过期知识缺口、重复模型、低质量题目和不匹配证据的学习画像
```

默认不要创建太多 Agent。多数学习者三个就够。

## OpenHanako 状态层

桌面端不一定必须使用 GitHub。

三选一：

```text
本地 git + Obsidian
本地 git 仓库
GitHub 仓库
```

如果学习者想要本地优先、快速编辑、私人笔记、Markdown 导航和 git 历史，本地 git + Obsidian 可能已经够用。

只有需要云同步、跨设备接手、公开模板展示或远程 AI 访问时，才优先使用 GitHub。

## OpenHanako 设置步骤

### 1. 安装并配置模型

按照 OpenHanako 首次启动流程配置：

```text
对话模型
→ 普通对话和辅导

小工具模型
→ 轻量任务、路由、摘要、文件检查

大工具模型
→ 记忆编译、深度分析、来源 / 模型提取、仓库维护

视觉模型
→ 截图、图示、手写笔记、可视化解释
```

### 2. 创建 GitLearnOS 工作区

本地文件夹作为受保护来源层：

```text
GitLearnOS-local/
├── textbooks/
├── screenshots/
├── papers/
├── raw-notes/
└── exports/
```

学习状态层：

```text
GitLearnOS-state/
├── dashboard.md
├── learner-profile.md
├── goals/
├── sources/
├── models/
├── knowledge-gaps/
├── reviews/
├── automations/
└── archive/
```

本地保存原始材料。状态层保存可检查的学习状态。

### 3. 配置 Maintainer Agent

```text
你是 GitLearnOS Maintainer。

你的任务是保持目标学习状态一致：dashboard.md、learner-profile.md、goals/、sources/、models/、knowledge-gaps/、reviews/、automations/ 和 archive/。

编辑前先判断文件权限、状态层权限、本地访问、记忆状态，以及当前操作是否安全。

不要把个人学习数据写进模板仓库。只写入用户选定的状态层。

汇报每个被修改的文件。
```

建议记忆：

```text
GitLearnOS 的事实源是用户选定的状态层。
本地文件是受保护来源材料。
learner-profile.md 是可检查的学习者记忆。
知识缺口连接模型和未来练习。
```

### 4. 配置 Source & Model Extractor Agent

```text
你是 GitLearnOS Source & Model Extractor。

拿到材料后，创建诚实的来源记录。标注来源是 complete、excerpt-only、local-only、missing 还是 uncertain。

从题目、笔记、论文或错误中提取可复用模型。

当学习者不能识别、应用、解释或迁移某个模型时，记录知识缺口。

除非 OpenHanako 确实给了你本地文件访问，否则不要声称读过本地文件。
```

输出位置：

```text
sources/
models/
knowledge-gaps/
```

### 5. 配置 Practice & Review Coach Agent

```text
你是 GitLearnOS Practice & Review Coach。

只根据状态层出题：learner-profile.md、最近模型、活跃知识缺口、来源记录和复习历史。

每道题都要链接到一个来源、模型或知识缺口条目。

练习后，建议如何更新 learner-profile.md 和下次复习日期。
```

输出位置：

```text
reviews/
automations/practice-generator/
```

### 6. 配置可选 Critic Agent

```text
你是 GitLearnOS Critic。

审查仓库中的模糊笔记、无支持摘要、过期知识缺口、重复模型、低质量练习题，以及和证据不匹配的 learner-profile 条目。

只做小而安全的修改。无法确定的内容加入队列，不要猜。
```

输出位置：

```text
automations/organizer-critic/
```

### 7. 使用 OpenHanako 频道或委派

推荐流程：

```text
Maintainer 接收用户请求。
Maintainer 把来源 / 模型工作委派给 Source & Model Extractor。
Maintainer 把出题工作委派给 Practice & Review Coach。
必要时让 Critic 审查结果。
Maintainer 最后写入或批准状态层更新。
```

必须让状态层成为共享状态，避免多个 Agent 各自在私有记忆里跑偏。

### 8. 把书桌当成本地来源 inbox

可以把这些文件放到对应 Agent 的书桌：

```text
教材摘录
截图
PDF 笔记
论文片段
原始错题
```

Agent 应该把它们转成来源记录或模型卡，而不是把原始文件一股脑塞进状态层。

### 9. 配置定时任务

定时任务用于维护，不用于无审查地重写仓库。

建议：

```text
每天或每两天：
→ 检查 dashboard、learner-profile.md、活跃知识缺口和到期复习

每周：
→ 运行 Organizer + Critic + Revision

每次学习后：
→ 更新 learner-profile.md，记录新知识缺口，安排下次复习
```

定时任务必须汇报实际读取和修改了什么。

### 10. 沙盒规则

OpenHanako 文件权限要收窄：

```text
读取本地来源文件夹
只写入 GitLearnOS 状态层或受控工作区
删除文件前先问
上传私人材料前先问
发布真实学习记录前先问
```

## 用 Claude Code 或 Codex 部署 OpenHanako

Claude Code、Codex、Cursor 和类似工具可以帮助部署 OpenHanako 本身。

用它们做：

```text
源码阅读
Node 版本检查
依赖安装
Electron 启动调试
server 调试
构建或打包排错
```

不要把它们当作本仓维护的日常 GitLearnOS 辅导层。

源码引导的部署清单和安全提示词见 `docs/zh-CN/deploy-openhanako-with-code-agents.md`。

## 最终选择规则

```text
原生日常学习对话
→ ChatGPT 或 Claude

桌面端多 Agent 和本地文件工作流
→ OpenHanako / HanaAgent

部署或调试 OpenHanako 源码
→ Claude Code / Codex / Cursor / CLI code agent

长期学习状态
→ GitHub 目标仓库、本地 git 或本地 git + Obsidian

原始来源材料
→ 默认留在本地文件夹，需要时只取小摘录
```
