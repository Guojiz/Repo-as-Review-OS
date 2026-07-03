# 开始使用

本页是给人类用户看的短入口。

完整首次部署流程请先看：

- [QUICKSTART.zh-CN.md](../../QUICKSTART.zh-CN.md)
- [常见问题](../../FAQ.zh-CN.md)
- [第一次实验指南](first-experiment-guide.md)
- [什么内容放进 GitHub](what-goes-into-github.md)
- [运行环境自适应](runtime-self-adaptation.md)

## 基本想法

Repo as Review OS 里有两个仓库角色：

```text
Repo as Review OS 仓库
→ 模板仓库
→ 方法、文档、skill、示例、规则

你的目标仓库
→ 个人学习仓库
→ 目标、来源、模型、复习、dashboard
```

不要把个人学习数据写进模板仓库。

## 首次部署

1. 创建一个空的或接近空的私有目标仓库。
2. 连接一个能读取模板仓并写入目标仓的 AI 工具。
3. 让 AI 先识别自己的运行环境和权限边界。
4. 让 AI 在目标仓库中创建最小结构。
5. 告诉 AI 你的第一个学习目标。

## 目标仓库最小结构

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

## 重要边界

本地工作区可以测试这套方法，但它不等于 GitHub-backed Review OS。

除非 AI 确实验证过，否则不能声称自己拥有 GitHub 写入权限、已经 push、已经创建 Issues 或已经完成远程仓库更新。

见 [本地运行说明](../local-runtime-note.md)。
