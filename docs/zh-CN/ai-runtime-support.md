# AI 运行环境支持

本页是补充说明。

当前主线运行路径请先读：

- [运行环境自适应](runtime-self-adaptation.md)
- [自动化运行环境矩阵](automation-runtime-matrix.md)
- [本地运行说明](../local-runtime-note.md)
- [Skill 与记忆运行层](skill-and-memory-runtime.md)

## 核心想法

Repo as Review OS 不绑定某一个 AI 产品。

只要一个 AI 工具能够读取指令、访问仓库、修改文件并汇报改动，它就可以承载这个系统。

## 必要能力

一个合适的运行环境应该具备：

1. 仓库访问能力；
2. 文件创建和修改能力；
3. 项目规则或长期记忆；
4. 权限边界；
5. 可选的本地工作区访问；
6. 改动汇报能力。

## 可用运行环境

这个系统可以用于：

- 带 GitHub 或 MCP 连接器的 ChatGPT；
- Codex 类 coding agent；
- Claude Code 类命令行工具；
- Cursor 或 Windsurf 类 AI 编辑器；
- 其他能理解仓库的 AI 工具。

项目应该描述能力，而不是强制绑定某一个品牌。

## 为什么记忆重要

AI 应该记住这个用户偏好：

```text
使用 GitHub 作为主要 Review OS 仓库。本地文件视为受保护来源。只有需要时才请求本地摘录。中文和英文放在不同文件里。
```

如果没有记忆或项目规则，用户每次都要重复同样的设置。

## 最小运行环境

```text
一个 AI 工具 + 一个目标 GitHub 仓库 + 一个规则文件
```

## 最佳运行环境

```text
一个主 AI 工具
+ GitHub 仓库连接器
+ 项目记忆或持久规则
+ 清楚的权限边界
+ 必要时上传本地文件摘录
```

## 本地优先路径

本地工作区可以测试这套方法，但本地访问不等于 GitHub 访问。

边界说明见 [本地运行说明](../local-runtime-note.md)。
