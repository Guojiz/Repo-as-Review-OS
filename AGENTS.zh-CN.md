# AI 接手入口

[English](AGENTS.md)

本文件给 ChatGPT、Codex、Claude Code、Cursor、Windsurf 和其他 AI Agent 使用。编辑本仓库或帮助用户搭建自己的 Repo as Review OS 仓库前，请先遵守这里的规则。

## 任务

Repo as Review OS 是一个基于 GitHub 的目标驱动型 AI 学习操作系统。

你的任务是帮助用户把分散的学习材料整理成结构化仓库：包含目标、来源记录、可复用模型、复习题单、间隔复习、控制台、自动化输出和运行规则。

## 先读

1. `README.zh-CN.md`
2. `START-HERE.zh-CN.md`
3. `OPERATING-MODEL.zh-CN.md`
4. `AGENT-RUNTIME.zh-CN.md`
5. `docs/zh-CN/skill-and-memory-runtime.md`
6. 如果环境支持 skill，再读 `skills/repo-as-review-os/SKILL.md`
7. `templates/zh-CN/` 中相关模板
8. `examples/` 中相关 demo

## 运行层规则

如果环境支持文件型 skill，使用：

```text
skills/repo-as-review-os/SKILL.md
```

如果环境不支持 skill，使用记忆、自定义指令、项目指令或仓库级指令，并参考：

```text
docs/zh-CN/skill-and-memory-runtime.md
```

Skill 给 AI 行为，记忆给 AI 稳定偏好，仓库文件保存当前学习状态。

## 应该做

- 修改前先判断自己的权限等级。
- 保持原始来源可追踪。
- 诚实标记不完整来源。
- 把摘要和完整来源分开。
- 把重复错题或笔记提取成可复用模型。
- 需要时加入间隔复习字段。
- 维护控制台和复习题单。
- 长文档尽量使用中英双文件结构。
- 优先做小而可审查的改动。
- 编辑后说明改了哪些文件。

## 不要做

- 不要编造缺失的学习上下文。
- 不要把摘要当作来源。
- 不要公开私人样例。
- 不要把有版权教材、考试页面、老师文件、私人截图或真实成绩记录放进公开仓库。
- 未明确要求时不要删除用户资料。
- 不要把长文档写成一句英文一句中文的混排。
- 不要为了仓库漂亮牺牲学习效果。

## 新用户仓库搭建

帮助用户创建自己的学习仓库时：

1. 确认仓库是公开还是私有。
2. 如果会存真实学习资料，建议使用私有仓库。
3. 复制或重建核心方法文件和模板。
4. 创建 `dashboard.md`。
5. 创建 `goals/main-goal.md`。
6. 创建 sources、models、reviews、templates、agents、automations、archive 等目录。
7. 加入 skill 运行层或记忆回退说明。
8. 汇报创建了什么。

## 输出格式

完成后报告：

```text
Changed files:
- path: what changed

Still missing:
- item or source needed

Next action:
- recommended next step
```
