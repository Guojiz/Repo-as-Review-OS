# 仓库即复习操作系统

[English](README.md)

**Repo as Review OS 是一个基于 GitHub 和人工智能协作的培训与复习系统。**

它不是普通资料夹，而是一套工作流：人类把一个 GitHub 仓库交给 AI，AI 帮助整理来源、题目模型、模板、控制台和接手规则。

## 只看到一句话怎么办

把这段复制给 ChatGPT、Codex 或其他 AI：

```text
请阅读这个仓库：https://github.com/Guojiz/Repo-as-Review-OS
先读 START-HERE.zh-CN.md、README.zh-CN.md 和 AGENTS.zh-CN.md。帮我搭建自己的 Review OS。先解释它是什么，再指导我创建或选择一个 GitHub 仓库，然后创建基础文档、AI 接手规则、模板和网站文案。
```

## AI 执行路径

1. 读取 `START-HERE.zh-CN.md`、`README.zh-CN.md` 和 `AGENTS.zh-CN.md`。
2. 用人话向用户解释这个系统。
3. 指导用户创建或选择一个 GitHub 仓库。
4. 搭建目录结构。
5. 创建来源规则、接手规则、模板和控制台。
6. 只使用虚构或清理后的示例。
7. 汇报创建或修改了哪些文件。

## 人类需要做什么

- 如果是真实复习资料，先使用私有仓库。
- 如果是公开模板，只放结构、方法和清理后的示例。
- 先只给 AI 一个仓库的权限，不要一开始给整个账号。
- 要求 AI 汇报每个新增或修改的文件。

## 建议目录

```text
Repo-as-Review-OS/
├── README.md
├── README.zh-CN.md
├── AGENTS.md
├── AGENTS.zh-CN.md
├── START-HERE.md
├── START-HERE.zh-CN.md
├── LICENSE
├── docs/
├── agents/
├── templates/
└── website/
```

## 给 AI Agent

修改文件前先阅读 `AGENTS.zh-CN.md`。如果使用英文环境，也可以读 `AGENTS.md`。

## 许可证

采用 MIT License，详见 `LICENSE`。
