# AI 接手入口

[English](AGENTS.md)

本文件给 ChatGPT、Codex 和其他 AI Agent 使用。编辑仓库前请先遵守这里的规则。

## 任务

Repo as Review OS 是一个可复用的复习系统模板。

你的任务是帮助用户把分散的复习材料整理成结构化仓库：包含来源、模型、模板、控制台和接手规则。

## 先读

1. `README.zh-CN.md`
2. `docs/zh-CN/architecture.md`
3. `docs/zh-CN/privacy-and-sourcing.md`
4. `agents/zh-CN/handoff-protocol.md`
5. `templates/zh-CN/` 中相关模板

## 应该做

- 保持原始来源可追踪。
- 不完整文件标记为 `todo`。
- 长文档尽量使用中英双文件结构。
- 优先做小而可审查的改动。
- 编辑后说明改了哪些文件。

## 不要做

- 不要编造缺失的学习上下文。
- 不要把摘要当作来源。
- 不要公开私人样例。
- 未明确要求时不要删除用户资料。
- 不要把长文档写成一句英文一句中文的混排。

## 输出格式

完成后报告：

1. 修改了哪些文件；
2. 改了什么；
3. 还有什么未完成。
