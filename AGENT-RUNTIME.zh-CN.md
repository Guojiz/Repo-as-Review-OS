# AI 运行指南

本指南给任何想运行 GitLearnOS 的 AI 工具使用。

它不绑定某一个产品。只要工具能读取仓库、修改文件、遵守项目规则并汇报改动，就可以使用这个系统。

## 先检查自己的能力

开始前，先判断自己处在哪个层级：

- 没有仓库权限；
- 只有只读仓库权限；
- 拥有一个仓库的写入权限；
- 拥有较广泛账号权限；
- 拥有本地工作区权限。

推荐默认状态：只拥有一个仓库的写入权限。

## 主要运行模型

使用一个主 AI 工作流。

不要默认假设多 Agent 系统。其他工具可以存在，但 GitLearnOS 应该能被一个有能力的 AI 工具维护。

## 先读

1. [START-HERE.zh-CN.md](START-HERE.zh-CN.md)
2. [README.zh-CN.md](README.zh-CN.md)
3. [QUICKSTART.zh-CN.md](QUICKSTART.zh-CN.md)
4. [docs/zh-CN/first-experiment-guide.md](docs/zh-CN/first-experiment-guide.md)
5. [docs/zh-CN/what-goes-into-github.md](docs/zh-CN/what-goes-into-github.md)
6. [docs/zh-CN/runtime-self-adaptation.md](docs/zh-CN/runtime-self-adaptation.md)
7. [docs/local-runtime-note.md](docs/local-runtime-note.md)
8. [docs/zh-CN/automation-runtime-matrix.md](docs/zh-CN/automation-runtime-matrix.md)
9. [docs/adaptive-memory-and-learner-profile.md](docs/adaptive-memory-and-learner-profile.md)
10. [docs/lightweight-skg-dpm.md](docs/lightweight-skg-dpm.md)
11. [AGENTS.zh-CN.md](AGENTS.zh-CN.md)

## GitHub 的角色

GitHub 是操作层。

它保存结构、学习画像、模板、控制台、索引、来源状态、知识缺口、清理后的示例、接手规则和网站文案。

## 本地的角色

本地存储是受保护的来源层。

它可以保存教材、PDF、扫描件、截图、私人笔记、老师文件和大型媒体。

除非用户上传，或运行环境确实有本地访问权限，否则不要声称自己读过本地文件。

## 记忆的角色

如果 AI 工具有记忆、项目规则或持久指令，应该保存这个偏好：

```text
使用 GitHub 作为主要 GitLearnOS 仓库。本地文件视为受保护来源。只有需要时才请求本地摘录。围绕目标、学习画像、来源记录、可复用模型、知识缺口、间隔复习、控制台和生成题单组织学习。中文和英文放在不同文件里。
```

## 默认安全操作

如果拥有指定仓库的写入权限，AI 可以：

- 创建文档；
- 更新模板；
- 更新控制台；
- 更新 learner-profile.md；
- 记录知识缺口；
- 把不完整文件标记为 `todo`；
- 添加清理后的示例；
- 汇报改动。

## 先问用户

删除文件、改变公开状态、上传本地私人文件、发布真实记录、接触密钥、修改许可证之前，必须先问用户。