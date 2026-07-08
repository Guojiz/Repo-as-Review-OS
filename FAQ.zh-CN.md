# 常见问题

## GitLearnOS 是什么？

GitLearnOS 是一套 GitHub 原生的学习轨迹操作系统，用于 AI 辅助学习。

它让 AI 工具把目标、学习画像、来源记录、可复用模型、知识缺口、复习题单、控制台和接手记录整理到一个目标仓库里。

## 这个仓库就是我的学习仓库吗？

不是。

这个仓库是模板仓库。

你自己的目标仓库才是保存个人学习记录的地方。

## 第一步应该做什么？

先创建一个空的或接近空的私有目标仓库。

然后让 AI 读取这个模板仓库，并把最小 GitLearnOS 结构部署到你的目标仓库里。

从 [QUICKSTART.zh-CN.md](QUICKSTART.zh-CN.md) 开始。

## 它能把学习数据整理到 GitHub 吗？

可以。

它整理的是结构化学习记录，例如目标、学习画像、来源记录、可复用模型、知识缺口、复习题单、控制台、下次复习日期和接手记录。

它不要求上传每个原始文件。

见 [什么内容放进 GitHub](docs/zh-CN/what-goes-into-github.md)。

## 我必须上传所有文件吗？

不需要。

大文件、原始截图、教材页面、其他软件导出的原始文件和本地工作文件，可以在需要时留在 GitHub 外面。

GitHub 主要保存结构化学习状态。

## 可以本地使用吗？

可以，但本地使用不等于 GitHub-backed GitLearnOS。

本地工作区可以测试方法，也可以编辑本地文件。但这不自动代表 AI 拥有 GitHub 权限。

见 [本地运行说明](docs/local-runtime-note.md)。

## 需要 GitHub Actions 吗？

不需要。

GitHub Actions 只是可选高级层，基础部署不需要。

## 需要 API key 吗？

不需要。

基础使用只需要一个能访问目标仓库的 AI 工具。API key 只适合高级自定义自动化。

## 哪些 AI 工具可以运行？

任何能读取模板仓库、访问目标仓库、修改文件并汇报改动的 AI 工具都可以运行。

例如带 GitHub connector 的 ChatGPT、Codex、Claude Code、Cursor、Windsurf、MCP worker 或其他能处理仓库的 AI agent。

## 怎么知道 AI 真的有 GitHub 权限？

让 AI 在部署前先识别运行环境和权限边界。

它应该说清楚自己能不能：

- 读取模板仓库；
- 读取目标仓库；
- 写入目标仓库；
- 只是使用本地文件；
- 是否需要你手动完成连接或授权步骤。

除非它能汇报实际改动了哪些文件，否则不能声称已经完成 GitHub 改动。

## 成功部署后应该长什么样？

目标仓库里应该有：

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

然后 AI 应该询问你的第一个学习目标。