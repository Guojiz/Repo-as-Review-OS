# DeepTutor 多 Agent 参考

本页记录 GitLearnOS 应该从 DeepTutor 多 Agent 模式里借鉴什么。

参考仓库与论文：

```text
https://github.com/HKUDS/DeepTutor
https://arxiv.org/abs/2604.26962
```

这是外部设计参考，不是 GitLearnOS 的产品身份。GitLearnOS 仍然来自原始 `zhongkao` 学习仓库模式，并继续把 GitHub / 本地 git 作为可检查的学习状态层。

## 论文到底说了什么

DeepTutor 区分两层：

```text
personalized agentic tutoring
→ 已验证的核心辅导 pipeline

proactive autonomous companionship / TutorBot
→ 跨渠道部署扩展
```

不要把这两层混成一句模糊的“很多 Agent”。

论文里的核心辅导闭环是：

```text
当前学习画像 + 相关历史 trace
→ 任务分发
→ 解题路径或出题路径
→ 生成 trace
→ 更新记忆 / 学习画像
```

### 解题路径

论文描述了三个顺序阶段：

```text
① Personalized Investigation
→ 拆解问题，收集来源证据和学习状态证据，制定计划

② Step-by-Step Solving
→ 用工具、观察、压缩和重规划执行子目标

③ Evidence-Based Writing
→ 生成带证据、符合学习者水平的最终解释
```

### 出题路径

论文描述了两个阶段：

```text
④ Idea Generation
→ 根据来源上下文和已诊断缺口生成候选练习想法
→ 筛选并排序想法

⑤ Critic-Guided Generation
→ 生成 question-answer-explanation 三元组
→ 验证正确性、结构匹配和必要的计算结果
```

### 记忆更新路径

论文把学习画像更新拆成三个记忆维度：

```text
Session History
→ 学过什么、难度、结果、表现趋势

Weakness Diagnosis
→ active / resolved 知识缺口、反复困惑、错误证据

Self-Reflection
→ 哪些讲法有效或失败，节奏、口吻、脚手架是否合适
```

### TutorBot 路径

论文里的 proactive agent loop 有三个大阶段：

```text
context assembly
→ persona / soul、memory、skills、conversation history

ReAct tool-calling loop
→ 调用 LLM、执行工具、追加观察，直到最终回答或预算耗尽

persist and consolidate
→ 追加 turn，压缩旧消息，更新长期 profile 和 session log
```

## 应该借鉴什么

DeepTutor 有价值的模式不是“创建很多 Agent 然后让它们都写状态”。

真正有价值的是：

```text
主 tutor loop
→ 需要时咨询或分派一个聚焦 Agent
→ 展示或记录 Agent 的运行过程
→ 回到主 loop
→ 主 loop 用自己的口吻回答
→ 长期状态只在一个受控位置写入
```

DeepTutor 的默认 Chat surface 可以在一个 turn 里调用工具、基于知识库 grounding、读取附件、写 notebook 记录，并在合适上下文中咨询 subagent。它的 README 里把 `rag`、`read_source`、`read_memory`、`write_memory`、`read_skill`、`load_tools`、`exec`、`ask_user`、`write_note`、`github` 和 `consult_subagent` 等描述为根据上下文挂载的工具。

DeepTutor 的 `consult_subagent` 工具也是一个很好的边界模型。模型只提供聚焦的 `question`；backend、工作目录、配置、预算和 session state 由服务端注入。被咨询的 Agent 展示自己的运行过程，返回最终答案；主模型在咨询预算用完后必须停止调用。

DeepTutor 的 subagent capability 还说明：咨询有 turn-scoped budget，被咨询 Agent 的 session 可以跨多次咨询延续，主模型最后应该用自己的口吻回答用户，而不是冒充 subagent。

## GitLearnOS 对 OpenHanako 的改造方式

对 GitLearnOS 来说，OpenHanako 多 Agent 应该使用**受控 pipeline + 咨询模式**，而不是无控制并行写入。

### 最小默认配置

给普通学习者默认使用：

```text
GitLearnOS Maintainer
→ 主 tutor loop
→ 负责 dashboard、learner-profile.md、索引、接手记录和最终写入

Source & Model Extractor
→ 在需要处理来源材料、错题、论文、截图或本地摘录时被咨询
→ 提出来源记录、可复用模型和知识缺口

Practice & Review Coach
→ 在需要复习题单、小测、间隔复习或下一步行动时被咨询
→ 提出练习和复习更新

Validator / Critic
→ 可选审查者
→ 检查无来源断言、过期缺口、弱题目、答案正确性和学习画像漂移
```

### DeepTutor-inspired 扩展 pipeline

只有用户想要更重的 OpenHanako 配置时才使用：

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

扩展 pipeline 是配置选项，不是 GitLearnOS 默认要求。

## 映射到 GitLearnOS 文件

```text
Personalized Investigation
→ sources/source-index.md
→ learner-profile.md
→ knowledge-gaps/gap-index.md
→ goals/main-goal.md

Step-by-Step Solving / Model Extraction
→ models/
→ sources/
→ knowledge-gaps/

Evidence-Based Writing
→ dashboard.md
→ reviews/
→ model cards
→ 面向学习者的解释笔记

Idea Generation
→ reviews/review-index.md
→ reviews/due.md
→ practice candidates

Critic-Guided Generation / Validation
→ answer keys
→ source links
→ difficulty fit
→ validator notes

Memory Update
→ learner-profile.md
→ agents/handoff-notes/latest.md
→ knowledge-gaps/gap-index.md
→ reviews/review-index.md
```

## 最终写入者规则

默认只有 Maintainer 写入长期状态。

其他 Agent 可以：

```text
检查
提出建议
提取模型
总结
出题
审查
验证
```

它们不应该独立重写 `learner-profile.md`、`dashboard.md`、`reviews/` 或 `knowledge-gaps/`，除非 Maintainer 明确委派写入并随后核对结果。

## 咨询预算规则

借鉴 DeepTutor 的 budget 思路：

```text
一次用户请求
→ 少量 subagent 咨询
→ 停止咨询
→ Maintainer 写入或汇报最终结果
```

推荐默认：

```text
普通任务：0-1 次咨询
来源较重任务：1-2 次咨询
复杂仓库修复：2-3 次咨询
扩展 pipeline 任务：需要用户明确批准
```

超过这个范围，通常说明系统开始漂移，应该询问学习者或写接手记录。

## 自包含问题规则

每次咨询 subagent 都应该自包含：

```text
任务：
上下文：
允许读取的文件或来源：
输出格式：
写入权限：
停止条件：
```

除非运行时明确传递完整上下文，否则不要假设 subagent 能看到父对话。

## 口吻规则

最终回答属于 Maintainer 或当前主运行层。

不要用 subagent 的身份回答。不要用 subagent 的第一人称说话。应该总结 subagent 找到了什么，再由主运行层做最终判断。

## 状态规则

学习状态层仍然是：

```text
GitHub 目标仓库
或本地 git
或本地 git + Obsidian
```

DeepTutor 可以启发 Agent pipeline 和咨询模式，但 GitLearnOS 状态仍然是文件化、可检查的。

## 不要复制什么

不要把 DeepTutor 的完整平台范围搬进 GitLearnOS 文档。

不要要求：

```text
完整 DeepTutor 安装
多用户部署
Knowledge Center / RAG engine stack
DeepTutor trace forest 实现
DeepTutor 三层记忆系统
partner workspace system
DeepTutor CLI
DeepTutor web app
```

这些是 DeepTutor 平台功能。GitLearnOS 只借鉴受控的多 Agent pipeline、咨询预算边界和学习状态反馈闭环。
