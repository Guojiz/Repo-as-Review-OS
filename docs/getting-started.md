# Getting Started / 开始使用

This guide is for a human user who wants ChatGPT, Codex, or another AI tool to help build a Review OS repository.  
本指南给人类用户使用：如果你想让 ChatGPT、Codex 或其他 AI 工具帮你搭建 Review OS 仓库，可以从这里开始。

## 1. Create a GitHub repository / 创建 GitHub 仓库

1. Open GitHub. / 打开 GitHub。
2. Click **New repository**. / 点击 **New repository**。
3. Choose a name, for example `my-review-os`. / 选择仓库名，例如 `my-review-os`。
4. Start private if you will store real study records. / 如果要放真实复习资料，建议先设为私有。
5. Add a license if you want others to reuse it. / 如果希望别人复用，添加许可证。

Recommended license for a public template: MIT License.  
公开模板推荐许可证：MIT License。

## 2. Give AI access / 给 AI 打开权限

If you use ChatGPT with GitHub tools, connect GitHub and allow access to the repository.  
如果你使用带 GitHub 工具的 ChatGPT，请连接 GitHub，并允许它访问这个仓库。

If you use Codex, open the repository as the project workspace and make sure it can read and edit files.  
如果你使用 Codex，请把这个仓库作为项目工作区，并确认它可以读取和编辑文件。

Use the least privilege that still works. Start with one repository, not your whole account.  
尽量使用最小权限：先只授权一个仓库，不要一开始就授权整个账号。

## 3. First prompt to AI / 给 AI 的第一条提示词

```text
Read README.md and AGENTS.md first. Help me initialize this repository as a Review OS. Keep all personal study records private. Create or update docs, agents, templates, and website copy. Use bilingual English-Chinese headings.

请先阅读 README.md 和 AGENTS.md。帮我把这个仓库初始化为 Review OS。个人复习资料保持私有。创建或更新 docs、agents、templates 和 website 文案。标题使用中英双语。
```

## 4. What to add first / 最先添加什么

Add these files or folders first:  
优先添加这些文件或目录：

- `AGENTS.md` / AI 接手入口；
- `README.md` / 项目总览；
- `docs/architecture.md` / 架构说明；
- `docs/privacy-and-sourcing.md` / 来源与公开规则；
- `agents/handoff-protocol.md` / 接手协议；
- `templates/problem-card.md` / 错题卡模板；
- `templates/dashboard.md` / 控制台模板。

## 5. Private first, public later / 先私有，后公开

A real review repository may contain personal learning records. Keep it private first.  
真实复习仓库可能包含个人学习记录，建议先保持私有。

When publishing, extract only:  
公开时只提取：

- structure / 结构；
- templates / 模板；
- fake examples / 虚构示例；
- method notes / 方法说明；
- deployment instructions / 部署说明。
