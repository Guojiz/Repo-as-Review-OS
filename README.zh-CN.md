# Repo as Review OS

[English](README.md)

**Repo as Review OS 是一个基于 GitHub 的目标驱动型 AI 学习操作系统。**

它不是普通资料夹，也不只是复习模板。它把一个 GitHub 仓库变成 AI 可以读取、写回、追踪、整理、出题和持续接手的学习时间线。

当前状态：早期公开版本。见 `PUBLIC-ALPHA.zh-CN.md`。

核心模型：

```text
目标
→ 来源
→ 拆解
→ 模型
→ 题单
→ 间隔复习
→ 自动化整理
→ 新理解
```

## 先看 demo

中文轻量示例：`examples/zh-CN/demo-zhongkao-lite/`

它展示了一个虚构的中考数学目标如何变成：

```text
主目标
→ 几何模型
→ 复习题单
→ 控制台
→ 下次复习
```

## 只看到一句话怎么办

把这段复制给 ChatGPT、Codex、Claude Code、Cursor、Windsurf 或其他能读写 GitHub 的 AI 工具：

```text
请阅读这个仓库：https://github.com/Guojiz/Repo-as-Review-OS
先读 OPERATING-MODEL.zh-CN.md、START-HERE.zh-CN.md、AGENT-RUNTIME.zh-CN.md 和 AGENTS.zh-CN.md，再看 examples/zh-CN/demo-zhongkao-lite。帮我搭建自己的 Review OS。先解释它是什么，再判断你的权限边界，然后指导我创建或选择一个 GitHub 仓库。接着创建目标文件、目录结构、来源规则、题目模型模板、间隔复习字段、自动化输出位置和控制台。
```

## 它解决什么问题

很多学习资料会散在聊天记录、截图、老师文件、笔记、错题本和本地文件夹里。

Repo as Review OS 不要求把所有东西一股脑丢进仓库。AI 应该先理解目标，再拆解、归纳、整理、回填、归档和生成新任务。

## 为什么要用 GitHub

GitHub 不只是网盘。它是一条可以写入的时间线。

它能记录：

- 文件什么时候改过；
- 改了什么；
- 为什么改；
- 哪些题目被拆成模型；
- 哪些内容到期该复习；
- 自动化上次整理或出题留下了什么。

普通 AI 项目可以保存指令和上下文，但不够提供开放文件树、结构化写回、版本历史和持久工作区。

## AI 执行路径

1. 判断自己的权限等级。
2. 读取用户目标。
3. 检查仓库结构。
4. 找到活跃来源、模型和薄弱点。
5. 判断什么要拆解、合并、重写、复习、生成或归档。
6. 更新文件。
7. 必要时安排下次复习。
8. 汇报每一次改动。

## 人类需要做什么

- 如果是真实学习资料，先使用私有仓库。
- 如果是公开模板，只放结构、方法和清理后的示例。
- 先只给 AI 一个仓库的权限，不要一开始给整个账号。
- 要求 AI 汇报每个新增或修改的文件。
- 本地教材、PDF、截图和老师文件可以留在本地，只在需要时上传最小摘录。

## 如何贡献

欢迎贡献：demo、模板、翻译、自动化提示词、文档改进和使用反馈。

请先阅读：

```text
CONTRIBUTING.zh-CN.md
PUBLIC-CHECKLIST.zh-CN.md
```

可以通过 GitHub Issues 提交反馈、demo 想法或 bug 报告。

## 关键文档

```text
OPERATING-MODEL.zh-CN.md        总运行模型
AGENT-RUNTIME.zh-CN.md          AI 运行指南
PUBLIC-ALPHA.zh-CN.md           早期公开说明
PUBLIC-CHECKLIST.zh-CN.md       公开前检查清单
CONTRIBUTING.zh-CN.md           贡献指南
examples/zh-CN/demo-zhongkao-lite/ 中文轻量 demo
docs/zh-CN/product-positioning.md 产品定位
docs/zh-CN/why-github.md        为什么使用 GitHub
docs/zh-CN/goal-model.md        目标模型
docs/zh-CN/adaptive-rules.md    动态规则
docs/zh-CN/spaced-repetition.md 间隔复习
docs/zh-CN/filesystem-design.md 文件系统设计
docs/zh-CN/automation-model.md  自动化模型
docs/zh-CN/lessons-from-original-system.md 从原系统提炼出的规则
```

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

## 给 AI Agent

修改文件前先阅读 `OPERATING-MODEL.zh-CN.md`、`AGENT-RUNTIME.zh-CN.md` 和 `AGENTS.zh-CN.md`。如果使用英文环境，也可以读对应英文文件。

## 许可证

采用 MIT License，详见 `LICENSE`。
