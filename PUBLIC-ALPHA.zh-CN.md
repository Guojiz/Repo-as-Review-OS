# 早期公开版本

GitLearnOS 已经是一套可以试用的早期学习套件。它可以交给具备工具能力的 AI Agent 检查、Fork 和运行，但学习协议与模板仍可能根据真实使用反馈调整。

仓库继续保留历史名称 `Repo-as-Review-OS`。

## 已可测试

- 简短的学习者与 Agent 入口；
- 按能力适配的 ChatGPT Work 与仓库 Agent 执行路径；
- 单一主 Agent 运行模型；
- 来源、学习画像、模型、知识缺口、复习和会话模板；
- 基于证据的 0–3 复习评分；
- 可复现的下次复习间隔；
- 可移植 Router 与专用 Skills；
- 从学习者尝试到状态写回完整闭环的中文 demo。

## 这样试用

```text
把 https://github.com/Guojiz/Repo-as-Review-OS 作为 GitLearnOS 模板仓库。
目标仓库：<私有仓库链接>
学习目标：<目标>

先读 START-HERE.zh-CN.md 与 AGENTS.zh-CN.md，检查目标仓库，然后直接进行第一次基于证据的学习会话。逐项汇报改动文件。
```

## 仍在实验

- 0–3 默认间隔是否适合所有学科；
- 学习画像假设应该多久升级或删除；
- 保存多少会话证据才不会让仓库变得嘈杂；
- 非考试场景 demo 与长期使用证据；
- Skill 套件在不同 Agent 产品中的安装与可移植性。

## 对标边界

港大 DeepTutor 是能力对标项目。GitLearnOS 是轻量套件，不声称功能或 Runtime 对等。原始 `zhongkao` 仓库是实践落实基线。

## 安全

真实学习记录使用私有目标仓库。版权原件、私人截图、老师文件、凭据和敏感信息不能放进公开模板。

欢迎通过 GitHub Issues 提交 Bug 与真实试用结果。
