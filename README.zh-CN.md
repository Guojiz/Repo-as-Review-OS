# GitLearnOS

![GitLearnOS 中文概览图](docs/assets/repo-as-review-os-map.zh-CN.svg)

[English](README.md)

**GitLearnOS / 学习轨迹操作系统，是给你用于学习的人工智能大脑，可以让你的学习更加高效、智能。**

仓库名暂时仍为 `Repo-as-Review-OS`，用于保持链接连续；项目展示名改为 **GitLearnOS**。

当前状态：早期公开版本。见 [PUBLIC-ALPHA.zh-CN.md](PUBLIC-ALPHA.zh-CN.md)。

## 适合谁

- 想把 AI 从一次性聊天变成长期学习助手的人；
- 想用 GitHub 保存学习轨迹、复习记录和知识结构的人；
- 想让 ChatGPT、Claude、智谱清言、本地 Agent 等不同 AI 都能接手同一套学习仓库的人；
- 想把目标、资料、错题、模型、知识缺口、复习计划和下一步行动统一管理的人。

它不是网盘，也不是单纯的笔记模板；它更像一套让 AI 可以持续接手学习过程的文件系统。

## 从哪里开始

按你的身份选入口：

- **学习者：**先读 [30 秒介绍](docs/zh-CN/30-second-intro.md)，再读 [快速开始](QUICKSTART.zh-CN.md)。
- **AI 工具：**先读 [START-HERE.zh-CN.md](START-HERE.zh-CN.md)、[AGENTS.zh-CN.md](AGENTS.zh-CN.md) 和 [AGENT-RUNTIME.zh-CN.md](AGENT-RUNTIME.zh-CN.md)，再根据运行环境继续读相关链接。
- **专家或贡献者：**先读 [与原系统的对齐分析](docs/zh-CN/parity-with-original-system.md)、[Product Positioning](docs/product-positioning.md)、[GitLearnOS Evaluation Standard](docs/agentic-tutoring-standard.md)、[Lightweight SKG and DPM](docs/lightweight-skg-dpm.md) 和 [Adaptive Memory and Learner Profile](docs/adaptive-memory-and-learner-profile.md)。

## 核心流程

```text
目标
→ 来源
→ 拆解
→ 模型
→ 知识缺口
→ 题单
→ 间隔复习
→ 控制台
→ 新理解
```

## 仓库角色

```text
Repo-as-Review-OS 仓库
→ 模板仓库
→ 方法、文档、skill、示例、规则

用户目标仓库
→ 个人 GitLearnOS 仓库
→ 目标、学习画像、来源、模型、知识缺口、复习、dashboard
```

AI 应该把这个仓库作为模板读取，然后把结构部署到用户自己的目标仓库里。

## 先看 demo

- [中文轻量 demo](examples/zh-CN/demo-zhongkao-lite/)

这个项目的主对标不是 HKU 或某个完整辅导平台，而是原始 `zhongkao` 学习仓库系统和清理后的 `demo-zhongkao-lite`：能不能把真实有效的学习闭环，变成更轻、更通用、可复用的 GitHub + AI 模板。

## 只看到一句话怎么办

把这段复制给任意有能力读写 GitHub 仓库的 AI 工具：

```text
请阅读这个模板仓库：https://github.com/Guojiz/Repo-as-Review-OS

仓库名是 Repo-as-Review-OS，但项目概念名是 GitLearnOS。

先读 START-HERE.zh-CN.md、README.zh-CN.md、QUICKSTART.zh-CN.md、AGENT-RUNTIME.zh-CN.md、AGENTS.zh-CN.md、docs/zh-CN/parity-with-original-system.md、docs/zh-CN/runtime-self-adaptation.md、docs/zh-CN/skill-and-memory-runtime.md、docs/adaptive-memory-and-learner-profile.md 和 docs/lightweight-skg-dpm.md。只在当前运行环境需要时继续读更深层链接。

帮我搭建自己的 GitLearnOS。先解释它是什么，再判断你当前的运行环境、权限边界、记忆能力、GitHub 访问能力，以及哪些步骤需要我手动完成。

请把这个 Repo-as-Review-OS 仓库视为模板仓库，把我的目标仓库视为个人学习仓库。不要把我的学习数据写进模板仓库。

然后指导我创建或选择一个目标 GitHub 仓库。如果你的环境支持 skill，就从 skills/repo-as-review-os/SKILL.md 开始；如果不支持 skill，就使用 docs/zh-CN/skill-and-memory-runtime.md 里的记忆回退方案。

接着在我的目标仓库里创建目标文件、learner-profile.md、目录结构、来源规则、题目模型模板、知识缺口字段、间隔复习字段、自动化输出位置和控制台。如果我已经给出学习目标，直接使用；如果没有，再问我的第一个学习目标。每次创建或修改文件都要汇报。
```

## 什么内容放进 GitHub

GitHub 主要保存结构化学习记录：目标、学习画像、来源记录、可复用模型、知识缺口、复习题单、控制台、下次复习日期和 AI 接手记录。

它不要求保存每个原始文件。更多说明见 [什么内容放进 GitHub](docs/zh-CN/what-goes-into-github.md)。

## ChatGPT Project 与记忆的边界

ChatGPT Project 适合放固定性的教材、少量稳定资料和项目说明，让 ChatGPT 在对话中读取和参考。

它不应该被当成完整学习仓库：动态笔记、大量材料、错题记录、复习历史、学习画像、题单归档和跨 Agent 接手状态，都应该以 GitHub 仓库为准。

ChatGPT 记忆适合保存稳定偏好和简短学习者摘要。它应该和 GitHub 同步校准，但不能替代 GitHub 的文件、索引和版本历史。

简单区分：

```text
ChatGPT 记忆 → 主动的稳定偏好缓存
ChatGPT Project → 固定资料架 + 对话层
GitHub 仓库 → 被动但可检查的长期学习状态 + 写回层 + 版本历史
本地文件夹 → 原始资料和工作文件层
```

如果 ChatGPT 记忆和 GitHub 内容冲突，优先相信 GitHub，再更新记忆或项目说明。

更多说明见 [本地文件夹与 ChatGPT Project 说明](docs/local-runtime-note.md) 和 [Adaptive Memory and Learner Profile](docs/adaptive-memory-and-learner-profile.md)。

## 静态与动态个性化

GitLearnOS 对齐两层：

```text
静态 grounding 层
→ 本地教材、来源记录、模型、GitHub 索引

动态学习者层
→ learner-profile.md、知识缺口、复习结果、AI 原生记忆、可选外部记忆工具
```

静态层负责把回答追溯到材料。动态层负责让解释、出题、复习和下一步行动对齐学习者。

见 [Lightweight SKG and DPM](docs/lightweight-skg-dpm.md)。

## 外部研究信号

DeepTutor 显示，将静态知识 grounding、动态学习者记忆和闭环辅导结合起来，可以让个性化辅导质量相对最强基线提升 **10.8%**，并让五个基础模型的通用推理平均提升 **28.6%**。这只作为支持性证据，说明“来源 grounding + 学习者状态 + 闭环练习”这类设计有潜力。GitLearnOS 不声称复刻 DeepTutor、港大的平台或任何完整辅导运行时。见 arXiv:2604.26962。

## 评价标准

这个项目应该首先对标原始 `zhongkao` 学习仓库系统：能不能在更轻、更通用的模板里，保留原系统的学习闭环、文件纪律、复习习惯、AI 接手能力和可检查进展。

见 [GitLearnOS Evaluation Standard](docs/agentic-tutoring-standard.md) 和 [与原系统的对齐分析](docs/zh-CN/parity-with-original-system.md)。外部辅导研究是设计参考，不是主基准。

## 为什么用 GitHub

GitHub 不只是网盘。它是一条可以写入的学习时间线。

它能记录：

- 文件什么时候改过；
- 改了什么；
- 为什么改；
- 哪些题目被拆成模型；
- 哪些内容到期该复习；
- AI 上次留下了什么接手记录。

普通 AI 项目可以保存指令和上下文，但不提供同样开放的文件树、结构化写回、版本历史和持久工作区。

## AI 执行路径

1. 判断自己的运行环境、记忆、文件访问和权限等级。
2. 区分模板仓库和目标学习仓库。
3. 读取用户目标。
4. 检查目标仓库结构。
5. 找到活跃来源、模型、学习画像和知识缺口。
6. 判断什么要拆解、合并、重写、复习、生成或归档。
7. 只在正确的目标仓库中更新文件。
8. 只把稳定偏好或重复模式建议写入原生记忆。
9. 必要时安排下次复习。
10. 汇报每一次改动。

## Skill 或记忆运行层

Skill 只是可选执行层，不是项目本体。

如果 AI 工具支持 skill，先使用总入口 router skill：[skills/repo-as-review-os/SKILL.md](skills/repo-as-review-os/SKILL.md)。

完整 skill suite 见 [skills/README.md](skills/README.md)。

如果 AI 工具不支持 skill，使用记忆或项目指令回退方案：[docs/zh-CN/skill-and-memory-runtime.md](docs/zh-CN/skill-and-memory-runtime.md)。

Skill 提供可执行规则，记忆提供稳定偏好，仓库保存当前学习状态。

## 关键文档

- [QUICKSTART.zh-CN.md](QUICKSTART.zh-CN.md)：五分钟开始
- [FAQ.zh-CN.md](FAQ.zh-CN.md)：常见问题
- [docs/zh-CN/30-second-intro.md](docs/zh-CN/30-second-intro.md)：30 秒介绍
- [docs/zh-CN/first-experiment-guide.md](docs/zh-CN/first-experiment-guide.md)：第一次实验指南
- [docs/zh-CN/what-goes-into-github.md](docs/zh-CN/what-goes-into-github.md)：什么内容放进 GitHub
- [docs/zh-CN/runtime-self-adaptation.md](docs/zh-CN/runtime-self-adaptation.md)：运行环境自适应
- [docs/zh-CN/parity-with-original-system.md](docs/zh-CN/parity-with-original-system.md)：与原始 zhongkao 系统对齐
- [docs/zh-CN/customer-clarity-checklist.md](docs/zh-CN/customer-clarity-checklist.md)：客户明确性检查清单
- [OPERATING-MODEL.zh-CN.md](OPERATING-MODEL.zh-CN.md)：总运行模型
- [AGENT-RUNTIME.zh-CN.md](AGENT-RUNTIME.zh-CN.md)：AI 运行指南
- [AGENTS.zh-CN.md](AGENTS.zh-CN.md)：AI 接手规则
- [skills/README.md](skills/README.md)：Skill suite 总览
- [docs/local-runtime-note.md](docs/local-runtime-note.md)：本地文件夹与 ChatGPT Project 说明
- [docs/adaptive-memory-and-learner-profile.md](docs/adaptive-memory-and-learner-profile.md)：自适应记忆与学习画像
- [docs/lightweight-skg-dpm.md](docs/lightweight-skg-dpm.md)：轻量静态/动态个性化映射
- [docs/tutoring-benchmark-source-reference.md](docs/tutoring-benchmark-source-reference.md)：外部辅导研究参考
- [templates/learner-profile.md](templates/learner-profile.md)：学习画像模板
- [docs/zh-CN/automation-runtime-matrix.md](docs/zh-CN/automation-runtime-matrix.md)：自动化运行环境矩阵
- [docs/agentic-tutoring-standard.md](docs/agentic-tutoring-standard.md)：GitLearnOS 评价标准
- [examples/zh-CN/demo-zhongkao-lite/](examples/zh-CN/demo-zhongkao-lite/)：中文轻量 demo

## 贡献与合作

欢迎通过 Issue、PR 或实际使用反馈参与这个项目，尤其是：

- 不同 AI 工具的部署记录；
- 新的学习场景 demo；
- 复习模板、题目模型和 dashboard 改进；
- 文档翻译、错别字修正和教程截图；
- 让更多 Agent 适配 GitHub MCP / 记忆能力的说明。

如果这个项目对你或你的 AI 有帮助，欢迎点 Star，方便之后继续使用和更新。

## 建议目录

```text
gitlearnos/
├── dashboard.md
├── learner-profile.md
├── goals/
├── inbox/
├── sources/
├── models/
├── knowledge-gaps/
├── reviews/
├── templates/
├── agents/
├── automations/
└── archive/
```

## 许可证

采用 MIT License，详见 [LICENSE](LICENSE)。
