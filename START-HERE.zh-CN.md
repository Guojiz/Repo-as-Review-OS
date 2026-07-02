# 从这里开始

Repo as Review OS 是一个基于 GitHub 的目标驱动型 AI 学习操作系统。

它帮助用户和 AI 工具把分散的学习材料整理成一个可写入、可追踪、可复盘的学习仓库。

## 复制给 AI 的第一句话

```text
请阅读这个仓库：https://github.com/Guojiz/Repo-as-Review-OS
先读 START-HERE.zh-CN.md、README.zh-CN.md、OPERATING-MODEL.zh-CN.md、AGENT-RUNTIME.zh-CN.md、AGENTS.zh-CN.md 和 docs/zh-CN/skill-and-memory-runtime.md，再看 examples/zh-CN/demo-zhongkao-lite、examples/en/demo-sat-lite 和 examples/en/demo-research-reading-lite。帮我搭建自己的 Review OS。先解释它是什么，再判断你的权限边界，然后指导我创建或选择一个 GitHub 仓库。如果你的环境支持 skill，就使用 skills/repo-as-review-os/SKILL.md；如果不支持 skill，就使用 docs/zh-CN/skill-and-memory-runtime.md 里的记忆回退方案。接着创建目标文件、目录结构、来源规则、模型模板、间隔复习字段、自动化输出位置和控制台。
```

## AI 应该怎么做

1. 先读本文件。
2. 再读 `README.zh-CN.md`。
3. 再读 `OPERATING-MODEL.zh-CN.md`。
4. 再读 `AGENT-RUNTIME.zh-CN.md`。
5. 再读 `AGENTS.zh-CN.md`。
6. 再读 `docs/zh-CN/skill-and-memory-runtime.md`。
7. 向用户解释这个系统。
8. 判断当前权限边界。
9. 指导用户创建或选择一个 GitHub 仓库。
10. 判断使用 skill 运行层，还是记忆回退方案。
11. 搭建目录结构、模板、目标文件、控制台和运行规则。
12. 汇报创建或修改了哪些文件。

## 人类应该怎么做

1. 创建或选择一个 GitHub 仓库。
2. 用 MCP、GitHub connector 或其他安全连接方式，把 AI 工具连接到仓库。
3. 真实学习资料优先放在私有仓库。
4. 有版权或隐私材料尽量留在本地，只在需要时上传最小摘录。
5. 要求 AI 每次汇报仓库改动。

## 核心想法

一个仓库可以成为学习的操作系统。

它应该包含：

- 目标；
- 来源记录；
- 可复用模型；
- 复习题单；
- 间隔复习字段；
- 控制台；
- 自动化输出；
- AI 运行规则；
- skill 或记忆回退说明。

## 运行层选择

如果 AI 工具支持 skill，使用：

```text
skills/repo-as-review-os/SKILL.md
```

如果 AI 工具不支持 skill，使用：

```text
docs/zh-CN/skill-and-memory-runtime.md
```

Skill 给 AI 行为，记忆给 AI 稳定偏好，仓库给 AI 当前学习状态。
