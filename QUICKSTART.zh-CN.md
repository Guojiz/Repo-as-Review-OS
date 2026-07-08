# 快速开始

如果你想试用 GitLearnOS，但不想一上来读完整个仓库，先看这一页。

## 你需要什么

你需要这些东西：

```text
这个模板仓库
+ 你自己的目标 GitHub 仓库
+ 一个能读取模板仓并写入目标仓的 AI 工具
+ 一个学习目标
```

目标仓库是用来保存你个人学习记录的地方。

AI 工具可以是带 GitHub connector 的 ChatGPT、Codex、Claude Code、Cursor、Windsurf，或者通过 MCP / GitHub 集成连接的其他 agent。

## 五分钟开始

### 1. 创建一个私有目标仓库

首次部署时，建议创建一个空的或接近空的私有仓库，然后让 AI 把 GitLearnOS 的结构搭进去。

如果目标仓库里已经有文件，要告诉 AI 先检查现有文件，不要直接覆盖。

如果你要存真实学习笔记、错题、截图、成绩、个人学习记录，建议使用私有仓库。

推荐仓库名：

```text
my-gitlearnos
```

### 2. 把 AI 工具连接到目标仓库

使用 MCP、GitHub connector 或其他安全连接方式。

一开始只给一个仓库的权限，不要直接给整个账号的大范围权限。

AI 应该先确认它是否真的能读取和写入目标仓库。如果不能，就必须明确说出来。

### 3. 把这段发给你的 AI 工具

```text
请阅读这个模板仓库：
https://github.com/Guojiz/Repo-as-Review-OS

请在这个目标仓库里搭建我的个人 GitLearnOS：
<粘贴你的仓库链接>

这是首次部署。除非你发现仓库里已经有文件，否则先把目标仓库视为空仓库或接近空仓库。如果发现已有文件，先检查，不要未经确认直接覆盖。

先读 START-HERE.zh-CN.md、README.zh-CN.md、QUICKSTART.zh-CN.md、docs/zh-CN/first-experiment-guide.md、docs/zh-CN/what-goes-into-github.md、docs/zh-CN/runtime-self-adaptation.md、AGENT-RUNTIME.zh-CN.md、AGENTS.zh-CN.md、docs/zh-CN/skill-and-memory-runtime.md、docs/adaptive-memory-and-learner-profile.md 和 docs/lightweight-skg-dpm.md。

如果你支持 skill，请使用 skills/repo-as-review-os/SKILL.md。如果不支持 skill，请使用 docs/zh-CN/skill-and-memory-runtime.md 里的记忆回退方案。

请创建一个最小学习仓库结构，包括 dashboard.md、learner-profile.md、goals/main-goal.md、sources/、models/、knowledge-gaps/、reviews/、templates/、agents/、automations/ 和 archive/。如果我已经给出学习目标，直接使用；如果没有，再问我的第一个学习目标。每次创建或修改文件后都要汇报。
```

### 4. 告诉 AI 你的第一个目标

例如：

```text
我想在 6 周内提升 SAT Reading and Writing。
```

```text
我想每周复盘数学错题。
```

```text
我想读三篇 AI 论文，并记住核心观点。
```

```text
我想整理日常英语学习。
```

### 5. 正常使用它

设置好之后，你可以直接说：

```text
根据我的仓库，给我生成一套 30 分钟复习题单。
```

```text
把这道错题整理成一个可复用模型，记录知识缺口，并安排复习。
```

```text
检查我的 dashboard，告诉我今天该学什么。
```

```text
根据我的知识缺口定制一套小测。
```

## 什么内容放进 GitHub

GitHub 主要保存结构化学习记录：目标、学习画像、来源记录、可复用模型、知识缺口、复习题单、控制台、下次复习日期和接手记录。

它不一定保存每个原始文件。见 [docs/zh-CN/what-goes-into-github.md](docs/zh-CN/what-goes-into-github.md)。

## 不要上传什么

不要把隐私或版权材料放进公开仓库。

尽量不要上传：

- 完整教材页面；
- 有版权的完整考试题目；
- 老师文件；
- 私人截图；
- 成绩报告；
- 身份信息、密码、token、cookie。

真实学习数据请优先使用私有仓库。

## 成功后应该长什么样

设置完成后，你的仓库里应该有：

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

AI 应该能回答：

```text
我现在的目标是什么？
我有哪些知识缺口？
我下次该复习什么？
我今天该做什么练习？
你刚刚改了哪些文件？
```

## 先看 demo

想先看例子，可以从这里开始：

- [examples/en/demo-sat-lite/](examples/en/demo-sat-lite/)
- [examples/en/demo-research-reading-lite/](examples/en/demo-research-reading-lite/)
- [examples/zh-CN/demo-zhongkao-lite/](examples/zh-CN/demo-zhongkao-lite/)
