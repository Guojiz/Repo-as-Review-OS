# Skill 与记忆运行层

不同 AI 环境加载规则的方式不一样。

GitLearnOS 主动支持两个运行层：

```text
ChatGPT 原生工作流
→ 日常学习对话、记忆校准、GitHub 辅助工作和轻量自动化接手

OpenHanako / HanaAgent 桌面工作流
→ 本地文件、多 Agent、Skills、定时任务、浏览器 / 电脑操作和更深入的文件自动化
```

Claude、Codex、Claude Code、Cursor 和其他代码 / CLI Agent 原则上仍然可以读写 GitLearnOS 文件结构，但本仓库不详细维护它们的配置教程。

选择运行路径前，AI 应该先识别自己当前处在哪个环境，再调整部署方式。见 `docs/zh-CN/runtime-self-adaptation.md` 和 `docs/zh-CN/platform-agent-configuration.md`。

## 推荐运行层级

```text
本仓详细支持的日常平台：ChatGPT
→ 推荐用于日常学习对话、推理、解释、写作、记忆校准、来源解读、GitHub 辅助工作和轻量复习生成

本仓详细支持的桌面端增强运行时：OpenHanako / HanaAgent
→ 推荐给需要本地文件、多 Agent、记忆、Skills、定时任务、浏览器 / 电脑操作和更深入自动化的用户

有限兼容：Claude / Codex / Claude Code / Cursor / 仓库型 CLI agents
→ 用户可以自行适配，但本仓不提供详细配置教程

轻量单上下文层：智谱清言、国产单上下文 Agent、其他聊天式 AI
→ 适合在一个上下文里读取少量规则、材料和仓库片段，执行简化版学习工作流
```

默认不要求用户再额外配置桌面 Agent。ChatGPT 已经可以通过原生平台能力完成很多日常学习流程。OpenHanako 是当用户需要本地文件访问、多 Agent 协作、Skills 和电脑侧定时任务时的桌面增强推荐。

完整配置提示词和 Agent 角色见 `docs/zh-CN/platform-agent-configuration.md`。

## 三条运行路径

```text
路径 A：ChatGPT 原生工作流
→ 使用 memory、project instructions、文件、连接器、MCP 或 GitHub 集成
→ 让原生记忆与 learner-profile.md 对齐
→ GitHub 保持事实源
→ 没有实时仓库工具时，自动化只作为接手卡

路径 B：OpenHanako / HanaAgent 桌面工作流
→ 配置 GitLearnOS Maintainer、Source & Model Extractor、Practice & Review Coach 和可选 Critic
→ 使用本地书桌文件作为受保护来源 inbox
→ 使用 GitHub 作为共享学习状态
→ 汇报每个真实仓库改动

路径 C：单上下文回退
→ 只粘贴当前任务需要的规则和摘录
→ 完成一个聚焦学习任务
→ 把有价值结果手动或通过工具写回 GitHub
```

## ChatGPT 原生路径

直接使用 ChatGPT。

AI 应该配置：

```text
稳定指令
+ 可用时的原生记忆或项目指令
+ 可用时的 GitHub connector / MCP / app 集成
+ learner-profile.md 同步
+ 来源 / 模型 / 知识缺口 / 复习工作流
```

建议记忆内容：

```text
使用 GitHub 作为我的 GitLearnOS 事实源。本地文件视为受保护来源材料。learner-profile.md 是可检查的学习者记忆。围绕目标、来源记录、可复用模型、知识缺口、间隔复习、控制台和生成题单来组织学习。如果原生记忆和 GitHub 冲突，优先相信 GitHub，并建议更新记忆。
```

## OpenHanako / HanaAgent 桌面路径

当用户需要桌面端增强运行时，使用 OpenHanako。

推荐 GitLearnOS Agent：

```text
GitLearnOS Maintainer
→ dashboard、learner-profile.md、索引、仓库结构、接手记录

Source & Model Extractor
→ 来源记录、模型提取、知识缺口记录

Practice & Review Coach
→ 个性化题单、复习记录、下次复习日期

可选 Critic
→ 审查模糊笔记、过期缺口、无来源结论、低质量题目和学习画像漂移
```

GitHub 必须作为共享状态，避免多个 Agent 各自在私有记忆里跑偏。

OpenHanako 的书桌文件可以作为本地来源 inbox。把本地材料转成来源记录和模型卡，不要把原始文件一股脑塞进 GitHub。

完整桌面配置见 `docs/zh-CN/platform-agent-configuration.md`。

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
repo-as-review-os                  GitLearnOS 总入口 / router
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
learner-profile.md
sources/
models/
knowledge-gaps/
reviews/
dashboard.md
automations/
```

## 单上下文 Agent 路径

一些 AI 工具只有一个上下文窗口，或者没有稳定的 skill / memory / GitHub 写回能力。

这种环境仍然可以使用 GitLearnOS 的轻量版：

1. 复制当前任务需要的仓库规则；
2. 粘贴相关目标、学习画像、来源、模型、知识缺口或错题片段；
3. 让 AI 在当前上下文里完成一次整理、拆解、记录缺口、出题或复习；
4. 把有价值的结果手动或通过工具写回 GitHub。

不要要求单上下文 Agent 假装自己有长期记忆。它可以执行当前任务，但长期状态仍以 GitHub 为准。

## 有限兼容路径

Claude、Codex、Claude Code、Cursor 和其他代码 / CLI Agent 仍然可以在理解文件结构的前提下读写 GitLearnOS 仓库。

本仓库不提供这些平台的详细配置教程。它们可以作为外部工作流、代码任务或用户自行维护的适配层使用。

## 新仓库创建后怎么做

用户创建新的学习仓库后，AI 应该把 GitLearnOS 的核心结构复制或重建到那个仓库里。

最小私人学习仓库：

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
docs/zh-CN/platform-agent-configuration.md
templates/
skills/
```

如果目标 AI 工具只支持一个 skill，只复制：

```text
skills/repo-as-review-os/
```

如果支持多个 skill，复制整个 `skills/` 目录。

如果目标 AI 工具只有一个上下文窗口，只复制当前任务需要的最小规则，不要塞入整套文档。

## 重要区分

Skill 给 AI 行为。

记忆给 AI 稳定偏好。

项目空间给 AI 固定资料和对话上下文。

仓库给 AI 当前学习状态。

桌面运行时给 AI 本地电脑侧执行能力。

不要把这些东西混成一个东西。