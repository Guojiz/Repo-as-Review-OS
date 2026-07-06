# Repo as Review OS

![Repo as Review OS 中文概览图](docs/assets/repo-as-review-os-map.zh-CN.svg)

[English](README.md)

**这是给你用于学习的人工智能大脑，可以让你的学习更加高效、智能。**

当前状态：早期公开版本。见 [PUBLIC-ALPHA.zh-CN.md](PUBLIC-ALPHA.zh-CN.md)。

## 适合谁

- 想把 AI 从一次性聊天变成长期学习助手的人；
- 想用 GitHub 保存学习轨迹、复习记录和知识结构的人；
- 想让 ChatGPT、Claude、智谱清言、本地 Agent 等不同 AI 都能接手同一套学习仓库的人；
- 想把目标、资料、错题、模型、复习计划和下一步行动统一管理的人。

它不是网盘，也不是单纯的笔记模板；它更像一套让 AI 可以持续接手学习过程的文件系统。

刚开始看？先读 [QUICKSTART.zh-CN.md](QUICKSTART.zh-CN.md)、[常见问题](FAQ.zh-CN.md)、[30 秒介绍](docs/zh-CN/30-second-intro.md)、[第一次实验指南](docs/zh-CN/first-experiment-guide.md) 和 [什么内容放进 GitHub](docs/zh-CN/what-goes-into-github.md)。

## 核心流程

```text
目标
→ 来源
→ 拆解
→ 模型
→ 题单
→ 间隔复习
→ 控制台
→ 新理解
```

## 仓库角色

```text
Repo as Review OS 仓库
→ 模板仓库
→ 方法、文档、skill、示例、规则

用户目标仓库
→ 个人学习仓库
→ 目标、来源、模型、复习、dashboard
```

AI 应该把这个仓库作为模板读取，然后把结构部署到用户自己的目标仓库里。

## 只看到一句话怎么办

把这段复制给任意有能力读写 GitHub 仓库的 AI 工具：

```text
请阅读这个模板仓库：https://github.com/Guojiz/Repo-as-Review-OS

先读 QUICKSTART.zh-CN.md、FAQ.zh-CN.md、docs/zh-CN/30-second-intro.md、docs/zh-CN/first-experiment-guide.md、docs/zh-CN/what-goes-into-github.md、docs/zh-CN/runtime-self-adaptation.md、OPERATING-MODEL.zh-CN.md、START-HERE.zh-CN.md、AGENT-RUNTIME.zh-CN.md、AGENTS.zh-CN.md、skills/README.md 和 docs/zh-CN/skill-and-memory-runtime.md。

帮我搭建自己的 Review OS。先解释它是什么，再判断你当前的运行环境、权限边界，以及哪些步骤需要我手动完成。

请把这个 Repo as Review OS 仓库视为模板仓库，把我的目标仓库视为个人学习仓库。不要把我的学习数据写进模板仓库。

然后指导我创建或选择一个目标 GitHub 仓库。如果你的环境支持 skill，就从 skills/repo-as-review-os/SKILL.md 开始；如果不支持 skill，就使用 docs/zh-CN/skill-and-memory-runtime.md 里的记忆回退方案。

接着在我的目标仓库里创建目标文件、目录结构、来源规则、题目模型模板、间隔复习字段、自动化输出位置和控制台。每次创建或修改文件都要汇报。
```

## 什么内容放进 GitHub

GitHub 主要保存结构化学习记录：目标、来源记录、可复用模型、复习题单、控制台、下次复习日期和 AI 接手记录。

它不要求保存每个原始文件。更多说明见 [什么内容放进 GitHub](docs/zh-CN/what-goes-into-github.md)。

## 为什么用 GitHub

GitHub 不只是网盘。它是一条可以写入的学习时间线。

它能记录：

- 文件什么时候改过；
- 改了什么；
- 为什么改；
- 哪些题目被拆成模型；
- 哪些内容到期该复习；
- AI 上次留下了什么接手记录。

普通 AI 项目可以保存指令和上下文，但不够提供开放文件树、结构化写回、版本历史和持久工作区。

## AI 执行路径

1. 判断自己的运行环境和权限等级。
2. 区分模板仓库和目标学习仓库。
3. 读取用户目标。
4. 检查目标仓库结构。
5. 找到活跃来源、模型和薄弱点。
6. 判断什么要拆解、合并、重写、复习、生成或归档。
7. 只在正确的目标仓库中更新文件。
8. 必要时安排下次复习。
9. 汇报每一次改动。

## 先看 demo

- [中文轻量 demo](examples/zh-CN/demo-zhongkao-lite/)

## Skill 或记忆运行层

如果 AI 工具支持 skill，先使用总入口 router skill：[skills/repo-as-review-os/SKILL.md](skills/repo-as-review-os/SKILL.md)。

完整 skill suite 见 [skills/README.md](skills/README.md)。

如果 AI 工具不支持 skill，使用记忆或项目指令回退方案：[docs/zh-CN/skill-and-memory-runtime.md](docs/zh-CN/skill-and-memory-runtime.md)。

Skill 给 AI 行为，记忆给 AI 稳定偏好，仓库给 AI 当前学习状态。

## 关键文档

- [QUICKSTART.zh-CN.md](QUICKSTART.zh-CN.md)：五分钟开始
- [FAQ.zh-CN.md](FAQ.zh-CN.md)：常见问题
- [docs/zh-CN/30-second-intro.md](docs/zh-CN/30-second-intro.md)：30 秒介绍
- [docs/zh-CN/first-experiment-guide.md](docs/zh-CN/first-experiment-guide.md)：第一次实验指南
- [docs/zh-CN/what-goes-into-github.md](docs/zh-CN/what-goes-into-github.md)：什么内容放进 GitHub
- [docs/zh-CN/runtime-self-adaptation.md](docs/zh-CN/runtime-self-adaptation.md)：运行环境自适应
- [docs/zh-CN/customer-clarity-checklist.md](docs/zh-CN/customer-clarity-checklist.md)：客户明确性检查清单
- [OPERATING-MODEL.zh-CN.md](OPERATING-MODEL.zh-CN.md)：总运行模型
- [AGENT-RUNTIME.zh-CN.md](AGENT-RUNTIME.zh-CN.md)：AI 运行指南
- [AGENTS.zh-CN.md](AGENTS.zh-CN.md)：AI 接手规则
- [skills/README.md](skills/README.md)：Skill suite 总览
- [docs/local-runtime-note.md](docs/local-runtime-note.md)：本地文件夹与 ChatGPT Project 说明
- [docs/zh-CN/automation-runtime-matrix.md](docs/zh-CN/automation-runtime-matrix.md)：自动化运行环境矩阵
- [examples/zh-CN/demo-zhongkao-lite/](examples/zh-CN/demo-zhongkao-lite/)：中文轻量 demo

## 贡献与合作

欢迎通过 Issue、PR 或实际使用反馈参与这个项目，尤其是：

- 不同 AI 工具的部署记录；
- 新的学习场景 demo；
- 复习模板、题目模型和 dashboard 改进；
- 文档翻译、错别字修正和教程截图；
- 让更多 Agent 适配 GitHub MCP / 记忆能力的说明。

如果这个项目对你或你的 AI 有帮助，欢迎点 Star，让它在下一次复习前不会沉进信息海。

## 建议目录

```text
review-os/
├── dashboard.md
├── goals/
├── inbox/
├── sources/
├── models/
├── reviews/
├── templates/
├── agents/
├── automations/
└── archive/
```

## 许可证

采用 MIT License，详见 [LICENSE](LICENSE)。