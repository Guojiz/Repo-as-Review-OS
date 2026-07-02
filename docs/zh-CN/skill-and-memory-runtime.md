# Skill 与记忆运行层

不同 AI 环境加载规则的方式不一样。

Repo as Review OS 同时支持两种模式：支持 skill 的 agent，以及靠记忆或项目指令驱动的聊天软件。

## 两条运行路径

```text
路径 A：支持 skill 的 agent
→ 安装或复制 skill suite
→ 从 router skill 开始
→ 根据任务切换到具体子 skill
→ 连接 GitHub 仓库
→ 运行学习仓库工作流

路径 B：靠记忆驱动的 AI App
→ 连接 GitHub 仓库
→ 把核心运行规则加入 memory / custom instructions / project instructions
→ 运行学习仓库工作流
```

## Skill 路径

有些 AI agent 支持可复用 skill 包。

先从总入口 router skill 开始：

```text
skills/repo-as-review-os/SKILL.md
```

任务明确后，再使用对应子 skill：

```text
skills/repo-as-review-os-setup/SKILL.md
skills/repo-as-review-os-source/SKILL.md
skills/repo-as-review-os-model/SKILL.md
skills/repo-as-review-os-review/SKILL.md
skills/repo-as-review-os-maintenance/SKILL.md
```

## Skill suite 分工

```text
repo-as-review-os                  总入口 / router
repo-as-review-os-setup            创建或迁移学习仓库
repo-as-review-os-source           把材料整理成来源记录
repo-as-review-os-model            提取可复用学习模型
repo-as-review-os-review           生成复习题单、小测或练习
repo-as-review-os-maintenance      检查、修复和维护仓库
```

skill suite 给 AI 提供稳定行为。

skill 不应该存放不断变化的个人学习数据。

变化的数据应该放在用户自己的仓库里：

```text
goals/
sources/
models/
reviews/
dashboard.md
automations/
```

## 记忆路径

有些 AI App 不一定支持 skill 包。

这种情况下使用记忆、自定义指令或项目指令。

建议记忆内容：

```text
使用 GitHub 作为我的个人学习 OS 的主要操作层。本地文件视为受保护来源材料。不要编造缺失来源。围绕目标、来源记录、可复用模型、间隔复习、控制台和生成题单来组织学习。每次仓库改动都要汇报。如果来源不完整，要诚实标记并加入待补队列，不要假装完整。
```

## 新仓库创建后怎么做

用户创建新的学习仓库后，AI 应该把 Repo as Review OS 的核心结构复制或重建到那个仓库里。

最小私人学习仓库：

```text
dashboard.md
goals/main-goal.md
sources/
models/
reviews/
templates/
agents/
automations/
archive/
```

最小公开模板仓库：

```text
README.md
OPERATING-MODEL.md
AGENT-RUNTIME.md
CONTRIBUTING.md
PUBLIC-ALPHA.md
docs/
templates/
examples/
skills/
```

## 应该复制什么

对个人学习仓库来说，复制方法和模板，不一定复制所有公开 demo。

推荐复制：

```text
OPERATING-MODEL.md
AGENT-RUNTIME.md
docs/zh-CN/goal-model.md
docs/zh-CN/adaptive-rules.md
docs/zh-CN/spaced-repetition.md
docs/zh-CN/filesystem-design.md
docs/zh-CN/automation-model.md
templates/
skills/
```

如果目标 AI 工具只支持一个 skill，只复制：

```text
skills/repo-as-review-os/
```

如果支持多个 skill，复制整个 `skills/` 目录。

## 重要区分

Skill 给 AI 行为。

记忆给 AI 稳定偏好。

仓库给 AI 当前学习状态。

不要把这三者混成一个东西。
