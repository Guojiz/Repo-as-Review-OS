# 平台 Agent 配置教程

本教程只详细维护 GitLearnOS 的两个主支持运行层：

```text
日常原生 AI 平台
→ ChatGPT

桌面端增强 Agent 运行时
→ OpenHanako / HanaAgent
```

Claude Code、Codex、Cursor 和其他代码 / CLI Agent 不是本仓维护的日常 GitLearnOS 辅导运行层。

它们有一个有用角色：

```text
OpenHanako 部署助手
→ 阅读 OpenHanako 源码
→ 安装依赖
→ 运行和调试 HanaAgent
→ 准备桌面端运行时
```

这个角色见 `docs/zh-CN/deploy-openhanako-with-code-agents.md`。

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
GitHub 读取权限：
GitHub 写入权限：
本地文件访问：
外部记忆工具：
桌面自动化：
需要用户手动完成的步骤：
```

没有实际能力时，不要声称已经编辑仓库、读取本地文件、完成定时任务或拥有长期记忆。

## 推荐平台图

```text
ChatGPT
→ 本仓详细支持的日常学习平台
→ 推理、解释、写作、记忆校准、GitHub 辅助工作和轻量自动化接手

OpenHanako / HanaAgent
→ 本仓详细支持的桌面端增强运行时
→ 本地文件、多 Agent、Skills、定时任务、浏览器 / 电脑操作和更深入的文件自动化

Claude Code / Codex / Cursor / CLI agents
→ 只作为 OpenHanako 部署和源码辅助工具
→ 不是本仓维护的日常 GitLearnOS 辅导平台

Claude 原生平台
→ 原则上兼容，但本仓不详细维护；偏好这些生态的用户请使用外部专门方案或自行适配
```

ChatGPT 作为原生 AI 平台使用，不写成桌面端运行时。

OpenHanako 是用户需要本机多 Agent 系统时的桌面端增强推荐。

## ChatGPT 原生配置

适合日常学习、解释、写作、复习和 GitHub 辅助维护。

### 1. 创建或选择目标仓库

真实学习数据建议使用一个私有 GitHub 仓库。

建议结构：

```text
dashboard.md
learner-profile.md
goals/main-goal.md
sources/
models/
knowledge-gaps/
reviews/
templates/
agents/
automations/
archive/
```

### 2. 添加 Project instructions 或固定启动提示词

核心指令：

```text
你正在帮我运行 GitLearnOS。

GitHub 是我的学习状态事实源。本地文件是受保护的原始资料。ChatGPT 记忆是主动偏好缓存，不是仓库本身。

行动前先识别你的运行环境、记忆、文件访问、GitHub 访问和权限边界。

学习时遵守这个闭环：
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习。

不要编造缺失来源。除非你能汇报具体改了哪些文件，否则不要声称已经修改仓库。
```

### 3. 谨慎使用 ChatGPT 记忆

建议写入的稳定记忆：

```text
用户使用 GitLearnOS 进行 AI 辅助学习。
GitHub 是学习状态事实源。
learner-profile.md 保存可检查的学习画像。
本地文件是受保护来源材料。
练习应该来自最近模型和活跃知识缺口。
如果 ChatGPT 记忆和 GitHub 冲突，优先相信 GitHub，并建议更新记忆。
```

不要把临时任务、原始私人笔记、过期知识缺口或一次性练习结果当作永久记忆。

### 4. 连接 GitHub 后先验证权限

```text
请检查你是否能读取我的目标仓库，以及是否能写入。汇报你的准确权限等级。如果你不能写入，不要假装可以更新文件。
```

### 5. 首次运行提示词

```text
请阅读这个模板仓库：https://github.com/Guojiz/Repo-as-Review-OS

帮我在这个目标仓库里搭建 GitLearnOS：
<粘贴目标仓库>

先识别你的运行环境、记忆能力、Project 上下文、GitHub 读写权限，以及我需要手动完成的步骤。

然后创建或检查 dashboard.md、learner-profile.md、goals/main-goal.md、sources/、models/、knowledge-gaps/、reviews/、templates/、agents/、automations/ 和 archive/。汇报每个创建或修改的文件。
```

### 6. 日常使用提示词

```text
请使用我的 GitLearnOS 仓库。

读取 dashboard.md、learner-profile.md、最近模型、活跃知识缺口和最近复习记录。

告诉我下一步应该学什么，生成一小套个性化练习，并说明每道题对应哪个来源、模型或知识缺口。

如果你更新仓库，请汇报每个被修改的文件。
```

### 7. 自动化边界

ChatGPT 的定时提示如果没有实时 GitHub 工具，只能算接手卡，不是已经完成仓库维护。

建议提示：

```text
这是 GitLearnOS 接手启动卡。如果你没有实时 GitHub 访问，不要声称仓库工作已完成。告诉我下一步要检查什么，以及应该在有工具权限的聊天里发送什么命令。
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
- 本地桌面工作区和书桌文件。

## 为什么 OpenHanako 适合 GitLearnOS

OpenHanako / HanaAgent 自己的说明里写了：它是有记忆、有性格、会主动行动，还能多个 Agent 在电脑上一同工作的 AI agent。

它的功能包括读写文件、命令、终端会话、浏览器、搜索、截图、网页检查、Skills、角色卡、多 Agent、书桌、定时任务、沙盒、插件和多平台接入。

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

GitHub 仓库作为学习状态层：

```text
GitLearnOS-repo/
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

本地保存原始材料。GitHub 保存可检查的学习状态。

### 3. 配置 Maintainer Agent

```text
你是 GitLearnOS Maintainer。

你的任务是保持目标 GitHub 仓库一致：dashboard.md、learner-profile.md、goals/、sources/、models/、knowledge-gaps/、reviews/、automations/ 和 archive/。

编辑前先判断文件权限、GitHub 权限、本地访问、记忆状态，以及当前操作是否安全。

不要把个人学习数据写进模板仓库。只写入用户自己的目标仓库。

汇报每个被修改的文件。
```

建议记忆：

```text
GitLearnOS 的事实源是用户目标 GitHub 仓库。
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

只根据仓库状态出题：learner-profile.md、最近模型、活跃知识缺口、来源记录和复习历史。

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
Maintainer 最后写入或批准仓库更新。
```

GitHub 必须作为共享状态，避免多个 Agent 各自在私有记忆里跑偏。

### 8. 把书桌当成本地来源 inbox

可以把这些文件放到对应 Agent 的书桌：

```text
教材摘录
截图
PDF 笔记
论文片段
原始错题
```

Agent 应该把它们转成来源记录或模型卡，而不是把原始文件一股脑塞进 GitHub。

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
只写入 GitLearnOS 目标仓库或受控工作区
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
日常学习对话
→ ChatGPT

桌面端多 Agent 和本地文件工作流
→ OpenHanako / HanaAgent

部署或调试 OpenHanako 源码
→ Claude Code / Codex / Cursor / CLI code agent

长期学习状态
→ GitHub 目标仓库

原始来源材料
→ 默认留在本地文件夹，需要时只取小摘录
```
