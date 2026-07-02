# 开始使用

本指南给人类用户使用：如果你想让 ChatGPT、Codex 或其他 AI 工具帮你搭建 Review OS 仓库，可以从这里开始。

## 1. 创建 GitHub 仓库

1. 打开 GitHub。
2. 点击 **New repository**。
3. 选择仓库名，例如 `my-review-os`。
4. 如果要放真实复习资料，建议先设为私有。
5. 如果希望别人复用，添加许可证。

公开模板推荐许可证：MIT License。

## 2. 给 AI 打开权限

如果你使用带 GitHub 工具的 ChatGPT，请连接 GitHub，并允许它访问这个仓库。

如果你使用 Codex，请把这个仓库作为项目工作区，并确认它可以读取和编辑文件。

尽量使用最小权限：先只授权一个仓库，不要一开始就授权整个账号。

## 3. 给 AI 的第一条提示词

```text
请先阅读 README.zh-CN.md 和 AGENTS.zh-CN.md。帮我把这个仓库初始化为 Review OS。个人复习资料保持私有。创建或更新 docs、agents、templates 和 website 文案。中文和英文请放在不同文件里。
```

## 4. 最先添加什么

优先添加这些文件或目录：

- `AGENTS.zh-CN.md`
- `README.zh-CN.md`
- `docs/zh-CN/architecture.md`
- `docs/zh-CN/privacy-and-sourcing.md`
- `agents/zh-CN/handoff-protocol.md`
- `templates/zh-CN/problem-card.md`
- `templates/zh-CN/dashboard.md`

## 5. 先私有，后公开

真实复习仓库可能包含个人学习记录，建议先保持私有。

公开时只提取：

- 结构；
- 模板；
- 虚构示例；
- 方法说明；
- 部署说明。
