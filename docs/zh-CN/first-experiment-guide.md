# 第一次实验指南

当新用户想试用 Repo as Review OS，但不清楚应该用哪个仓库时，先看这一页。

## 两个仓库的关系

```text
Repo as Review OS 仓库
→ 模板仓库
→ 方法、文档、skill、示例、规则

你自己的空仓库
→ 个人学习仓库
→ 你的目标、来源、模型、复习、dashboard
```

不要把个人学习数据直接写进模板仓库。

AI 应该先读模板仓库，再把结构部署到用户自己的仓库里。

## 推荐第一次实验流程

1. 新建一个空的私有仓库。
2. 把 Repo as Review OS 链接发给 AI。
3. 把你的空目标仓库链接发给 AI。
4. 让 AI 先识别自己的运行环境和权限边界。
5. 让 AI 部署最小结构。
6. 再告诉 AI 第一个学习目标。

## 给 ChatGPT 的提示词

```text
请阅读这个模板仓库：
https://github.com/Guojiz/Repo-as-Review-OS

然后把 Repo as Review OS 的最小结构部署到我的空目标仓库：
<粘贴你的目标仓库链接>

请先识别你的运行环境和权限边界：
- 你能不能读取模板仓库？
- 你能不能读取目标仓库？
- 你能不能写入目标仓库？
- 是否需要我手动开启 connector、app 或权限？

不要未经确认覆盖已有文件。
部署完成后，先问我的第一个学习目标。
```

## 给 Codex 或本地 coding agent 的提示词

```text
请把 Repo as Review OS 仓库作为模板和文档来源。
请把我的新空仓库或本地空文件夹作为目标学习仓库。

不要把个人学习数据写进模板仓库。

请在目标仓库中创建最小结构：
- dashboard.md
- goals/main-goal.md
- sources/
- models/
- reviews/
- templates/
- agents/
- automations/
- archive/

汇报每一个创建或修改的文件。
然后问我的第一个学习目标。
```

## 如果下载到本地

本地使用时也要保留同样关系：

```text
本地 Repo as Review OS 副本
→ 参考模板

本地 my-learning-os 文件夹
→ 目标学习仓库
```

AI 可以读取模板文件夹，但应该把学习状态写入目标文件夹。

## 部署完成后应该有什么

目标仓库里应该出现：

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

然后 AI 应该问：

```text
你希望这个仓库支持的第一个学习目标是什么？
```

## 常见误解

```text
错误：
把 Repo as Review OS 仓库本身当成自己的学习仓库。

正确：
把 Repo as Review OS 当模板，把结构部署到自己的仓库。
```

```text
错误：
还没部署好就直接发一道题，期待 AI 自动知道写到哪里。

正确：
先部署目标仓库，再发送目标、题目、笔记或复习任务。
```

```text
错误：
以为每个 AI 工具连接 GitHub 的方式都一样。

正确：
让 AI 先识别运行环境，并说明哪些步骤需要用户手动完成。
```
