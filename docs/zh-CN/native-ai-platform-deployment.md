# 原生 AI 平台部署指南

本指南覆盖 GitLearnOS 最应该当作参考实现的两个原生 AI 平台：

```text
ChatGPT
→ 原生记忆优先的学习平台

Claude
→ 原生项目 / artifact 优先的学习平台
```

其他聊天式 AI 平台基本可以照这两个平台的模式适配。

不要把 Claude 和 Claude Code 混在一起。Claude 是 claude.ai 或 Claude App 里的原生聊天平台。Claude Code 是代码 Agent，属于 OpenHanako 部署路径，不属于日常学习运行层。

## 核心规则

一次只使用一个活跃学习平台。

```text
一个学习者
→ 一个活跃原生 AI 平台
→ 一个学习状态层
→ 一条接手路径
```

今天用 ChatGPT，ChatGPT 就是活跃运行层。

今天用 Claude，Claude 就是活跃运行层。

不要让两个平台同时更新 learner-profile、knowledge-gaps、reviews 或 dashboard。

## 共同学习闭环

ChatGPT 和 Claude 都应该运行同一套 GitLearnOS 闭环：

```text
来源
→ 模型
→ 知识缺口
→ 个性化题目
→ 复习结果
→ learner-profile.md
→ 下次复习
```

平台可以记住偏好，但长期学习状态必须保存在可检查的状态层。

状态层可以是：

```text
GitHub 仓库
本地 git 仓库
本地 git + Obsidian vault
```

需要云同步、跨设备接手、公开模板或远程 AI 访问时，优先用 GitHub。

主要在一台电脑上学习、偏好本地优先时，本地 git + Obsidian 已经够用。

## ChatGPT 部署

当学习者想要最顺滑的手机 / 网页日常学习流程，以及较强的持续个性化时，使用 ChatGPT。

### 1. 选择状态层

三选一：

```text
GitHub 目标仓库
本地 git 仓库
本地 git + Obsidian vault
```

最小结构：

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

### 2. 创建 Project 或固定启动提示词

核心指令：

```text
你正在帮我在 ChatGPT 中运行 GitLearnOS。

使用我选定的状态层作为学习状态事实源。ChatGPT 记忆是主动偏好缓存，不是仓库本身。

行动前先识别你的运行环境、记忆、文件访问、仓库访问和权限边界。

遵守这个闭环：
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习。

不要编造缺失来源。除非你能说出具体改了哪些文件，否则不要声称已经编辑文件或仓库。
```

### 3. 配置记忆

只保存稳定偏好：

```text
用户使用 GitLearnOS 进行 AI 辅助学习。
选定状态层是学习状态事实源。
learner-profile.md 保存可检查的学习画像。
练习应该来自最近模型和活跃知识缺口。
如果记忆和状态层冲突，优先相信状态层，并建议更新记忆。
```

不要把临时任务、原始私人笔记、过期缺口或一次性练习结果当成永久记忆。

### 4. 日常提示词

```text
请使用我的 GitLearnOS 状态。

读取 dashboard.md、learner-profile.md、最近模型、活跃知识缺口和最近复习记录。

告诉我下一步应该学什么。生成一小套个性化练习，并说明每道题对应哪个来源、模型或知识缺口。

如果你更新文件，请汇报每个被修改的文件。
```

### 5. 定时提示边界

如果 ChatGPT 的定时提示没有实时仓库工具，就只能算接手启动卡。

```text
这是 GitLearnOS 接手启动卡。如果你没有实时仓库访问，不要声称仓库工作已完成。告诉我下一步要检查什么，以及应该在有工具权限的聊天里运行什么命令。
```

## Claude 部署

当学习者需要长上下文阅读、写作、Artifacts、项目式组织和精细草稿时，使用 Claude。

### 1. 选择状态层

三选一：

```text
GitHub 目标仓库
本地 git 仓库
本地 git + Obsidian vault
```

状态层仍然是事实源。

Claude Projects、项目文件、Artifacts 和记忆是工作表面，不是长期学习状态本身，除非用户只是做一次短实验。

### 2. 创建 Claude Project 或等价工作区

每个主要学习工作流使用一个 Claude Project。

只放稳定参考文件和说明。

不要把所有材料一股脑塞进 Project。Project 要轻，Claude 才容易遵守。

### 3. 添加 Claude 项目指令

```text
你正在帮我在 Claude 中运行 GitLearnOS。

使用我选定的状态层作为学习状态事实源。Claude project context、artifacts 和 memory 是工作表面，不是长期状态本身。

行动前先识别你的运行环境、记忆 / project 能力、文件访问、仓库访问和权限边界。

遵守这个闭环：
来源 → 模型 → 知识缺口 → 个性化题目 → 复习结果 → learner-profile.md → 下次复习。

不要编造缺失来源。除非你能说出具体改了哪些文件，否则不要声称已经编辑文件或仓库。

Artifacts 可以用于草稿、可视化解释、表格、小练习或临时教学材料。重要学习状态必须写回 learner-profile.md、sources/、models/、knowledge-gaps/、reviews/ 或 dashboard.md。
```

### 4. Claude 记忆和项目上下文规则

Claude 记忆或 Project context 只保存稳定偏好和长期工作假设。

适合保存：

```text
偏好解释方式
当前学习目标
状态层位置
仓库结构
反复出现的学习模式
格式约定
```

不要只存在记忆里：

```text
活跃知识缺口
一次性练习答案
临时截止日期
原始私人笔记
未经验证的来源结论
```

### 5. Claude 日常提示词

```text
请使用我的 GitLearnOS 状态。

从我提供的文件或连接仓库读取 dashboard.md、learner-profile.md、最近模型、活跃知识缺口和最近复习记录。

给出下一步行动，然后生成一小套练习。每道题都要说明对应哪个来源、模型或知识缺口。

只有在有助于复习、可视化或编辑结果时才使用 artifact。重要状态要写回选定状态层。
```

### 6. Claude artifact 规则

Artifacts 适合：

```text
课程草稿
可视化解释
交互式小练习
对比卡片
小 dashboard
写作修改
```

Artifacts 不应该变成唯一的学习状态保存地。

如果 artifact 产生了长期有用的学习信息，就把摘要写回状态层。

## 在 ChatGPT 和 Claude 之间切换

切换必须明确接手：

```text
1. 读取 dashboard.md 和 learner-profile.md。
2. 读取最近 models、knowledge-gaps 和 reviews。
3. 写接手记录。
4. 停止旧平台。
5. 新平台从接手记录开始。
```

不要让两个平台同时更新同一份学习状态。

## 其他平台怎么抄

其他原生 AI 平台可以照 ChatGPT / Claude 模式抄：

```text
原生记忆或项目上下文
→ 稳定偏好缓存

文件、artifact 或项目上传
→ 工作表面

GitHub / 本地 git / Obsidian
→ 长期学习状态

接手记录
→ 安全切换平台
```

如果一个平台说不清楚它读了什么、记住了什么、改了什么，那就只把它当单上下文助手。

## 和 OpenHanako 的关系

OpenHanako 不是 ChatGPT 或 Claude 这种网页 / 移动原生 AI 平台的替代品。

它是桌面端增强路径，用于本地文件、书桌文件、Skills、定时任务、外部入口和多 Agent 工作流。

当学习者想让电脑本身成为 Agent 工作区时，使用 OpenHanako。

Claude Code、Codex 或 Cursor 只用来部署或调试 OpenHanako。部署完成后，日常学习交回 OpenHanako。