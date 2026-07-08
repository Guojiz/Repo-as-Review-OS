# 从这里开始

GitLearnOS / 学习轨迹操作系统，是一个基于 GitHub 的轻量级 AI 学习系统。

它帮助用户和 AI 工具把分散的学习材料整理成一个可写入、可追踪、可复盘的学习仓库。

## 复制给 AI 的第一句话

```text
请阅读这个仓库：https://github.com/Guojiz/Repo-as-Review-OS

仓库名 Repo-as-Review-OS 用于保持链接连续。项目概念名是 GitLearnOS。

先读 START-HERE.zh-CN.md、README.zh-CN.md、QUICKSTART.zh-CN.md、AGENT-RUNTIME.zh-CN.md、AGENTS.zh-CN.md、docs/zh-CN/runtime-self-adaptation.md、docs/zh-CN/skill-and-memory-runtime.md、docs/adaptive-memory-and-learner-profile.md 和 docs/source-and-learner-state.md。只在当前运行环境需要时继续读更深层链接。

帮我搭建自己的 GitLearnOS。先解释它是什么，再判断你当前的运行环境、权限边界、记忆能力、GitHub 访问能力，以及哪些步骤必须由我手动完成。然后指导我创建或选择一个目标 GitHub 仓库。

请把这个 Repo-as-Review-OS 仓库视为模板仓库，把我的目标仓库视为个人学习仓库。不要把我的学习数据写进模板仓库。

如果你的环境支持 skill，就使用 skills/repo-as-review-os/SKILL.md；如果不支持 skill，就使用 docs/zh-CN/skill-and-memory-runtime.md 里的记忆回退方案。

接着在我的目标仓库里创建目标文件、learner-profile.md、目录结构、来源规则、模型模板、知识缺口字段、间隔复习字段、自动化输出位置和控制台。如果我已经给出学习目标，直接使用；如果没有，再问我的第一个学习目标。每次创建或修改文件都要汇报。
```

## AI 应该怎么做

1. 先读本文件。
2. 再读 `README.zh-CN.md`。
3. 再读 `QUICKSTART.zh-CN.md`。
4. 再读 `docs/zh-CN/runtime-self-adaptation.md`。
5. 再读 `AGENT-RUNTIME.zh-CN.md`。
6. 再读 `AGENTS.zh-CN.md`。
7. 再读 `docs/zh-CN/skill-and-memory-runtime.md`。
8. 再读 `docs/adaptive-memory-and-learner-profile.md`。
9. 再读 `docs/source-and-learner-state.md`。
10. 向用户解释这个系统。
11. 判断当前运行环境、记忆能力、文件访问和权限边界。
12. 区分模板仓库和目标学习仓库。
13. 指导用户创建或选择一个目标 GitHub 仓库。
14. 判断使用 skill 运行层、原生记忆、项目指令，还是单上下文回退方案。
15. 在目标仓库中搭建目录结构、模板、目标文件、学习画像、知识缺口、控制台和运行规则。
16. 汇报创建或修改了哪些文件。

## 人类应该怎么做

1. 创建或选择一个用于个人学习数据的目标 GitHub 仓库。
2. 用 MCP、GitHub connector 或其他安全连接方式，把 AI 工具连接到目标仓库。
3. 真实学习资料优先放在私有仓库。
4. 受保护或私人材料尽量留在本地，只在需要时上传最小摘录。
5. 要求 AI 每次汇报仓库改动。

## 核心想法

一个仓库可以成为学习的操作系统。

它应该包含：

- 目标；
- 学习画像；
- 来源记录；
- 可复用模型；
- 知识缺口；
- 复习题单；
- 间隔复习字段；
- 控制台；
- 自动化输出；
- AI 运行规则；
- skill 或记忆回退说明。

## 运行层选择

选择运行路径前，先读：

```text
docs/zh-CN/runtime-self-adaptation.md
docs/zh-CN/automation-runtime-matrix.md
docs/adaptive-memory-and-learner-profile.md
```

如果 AI 工具支持 skill，使用：

```text
skills/repo-as-review-os/SKILL.md
```

如果 AI 工具不支持 skill，使用：

```text
docs/zh-CN/skill-and-memory-runtime.md
```

Skill 给 AI 行为，记忆给 AI 稳定偏好，仓库给 AI 当前学习状态。
