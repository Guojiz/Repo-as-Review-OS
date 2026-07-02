# Repo as Review OS / 仓库即复习操作系统

A deployable review-system template built on GitHub and Markdown.  
一个基于 GitHub 和 Markdown 的可部署复习系统模板。

The idea is simple: treat a repository as the operating system for study. Notes, mistakes, reusable methods, writing drafts, source checks, and handoff rules should live in one structured place instead of being scattered across chats and screenshots.

核心想法很简单：把一个仓库当成复习的操作系统。笔记、错题、可复用方法、写作草稿、来源检查和接手规则，不应该散落在聊天记录和截图里，而应该进入一个清晰的结构。

## Goals / 目标

- Keep original sources traceable. / 保持原始材料可追踪。
- Turn mistakes into reusable models. / 把错题转化为可复用模型。
- Separate originals, summaries, indexes, and TODO items. / 区分原文、摘要、索引和待补项。
- Give future tools a clear map before they edit anything. / 让后续工具在编辑前先有地图。
- Publish only cleaned and non-private method-level content. / 只公开清理后的方法层内容。

## Suggested layout / 建议目录

```text
Repo-as-Review-OS/
├── README.md
├── LICENSE
├── docs/
├── agents/
├── templates/
└── website/
```

## Main layers / 主要层级

- `docs/`: architecture, deployment, privacy, and sourcing notes. / 架构、部署、隐私与来源规则。
- `agents/`: handoff rules and maintenance protocols. / AI 或后续编辑者的接手与维护规则。
- `templates/`: reusable cards for problems, writing materials, daily review, and dashboards. / 错题卡、写作素材卡、每日复盘和控制台模板。
- `website/`: public page copy for a personal site or project page. / 个人网站或项目页文案。

## Minimum workflow / 最小工作流

1. Add a source, mistake, draft, or feedback item. / 加入原始材料、错题、草稿或反馈。
2. Mark its status: original, summary, index, model, or TODO. / 标记状态：原文、摘要、索引、模型或待补。
3. Convert reusable items into templates. / 把可迁移内容转化为模板。
4. Use the handoff rules before editing the repository. / 编辑前先读接手规则。
5. Deploy only cleaned public-facing content. / 只部署清理后的公开内容。

## License / 许可证

MIT License. See `LICENSE`.  
采用 MIT License，详见 `LICENSE`。
