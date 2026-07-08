# AI 接手入口

[English](AGENTS.md)

本文件给 ChatGPT、Codex、Claude Code、Cursor、Windsurf 和其他 AI Agent 使用。编辑本仓库或帮助用户搭建自己的 GitLearnOS 仓库前，请先遵守这里的规则。

## 任务

GitLearnOS / 学习轨迹操作系统，是一个基于 GitHub 的轻量级 AI 学习系统。

你的任务是帮助用户把分散的学习材料整理成结构化仓库：包含目标、学习画像、来源记录、可复用模型、知识缺口、复习题单、间隔复习、控制台、自动化输出和运行规则。

## 先读

1. `README.zh-CN.md`
2. `START-HERE.zh-CN.md`
3. `QUICKSTART.zh-CN.md`
4. `docs/zh-CN/first-experiment-guide.md`
5. `docs/zh-CN/runtime-self-adaptation.md`
6. `docs/zh-CN/automation-runtime-matrix.md`
7. `docs/local-runtime-note.md`
8. `OPERATING-MODEL.zh-CN.md`
9. `AGENT-RUNTIME.zh-CN.md`
10. `docs/zh-CN/skill-and-memory-runtime.md`
11. `docs/adaptive-memory-and-learner-profile.md`
12. `docs/lightweight-skg-dpm.md`
13. 如果环境支持 skill，再读 `skills/repo-as-review-os/SKILL.md`
14. `templates/zh-CN/` 中相关模板
15. `examples/` 中相关 demo

## 运行层规则

行动前先识别当前运行环境：

```text
当前环境：
读取权限：
写入权限：
是否支持 skill：
memory / project instructions 回退：
需要用户手动完成的步骤：
```

如果环境支持文件型 skill，使用：

```text
skills/repo-as-review-os/SKILL.md
```

如果环境不支持 skill，使用记忆、自定义指令、项目指令或仓库级指令，并参考：

```text
docs/zh-CN/skill-and-memory-runtime.md
```

Skill 给 AI 行为，记忆给 AI 稳定偏好，仓库文件保存当前学习状态。

## 仓库角色

帮助新用户时，必须区分：

```text
Repo-as-Review-OS 仓库
→ 模板仓库
→ 方法、文档、skill、示例、规则

用户目标仓库
→ 个人 GitLearnOS 仓库
→ 目标、学习画像、来源、模型、知识缺口、复习、dashboard
```

不要把个人学习数据写进模板仓库。

## 应该做

- 修改前先判断自己的权限等级。
- 区分模板仓库和目标学习仓库。
- 需要用户手动完成 app、connector、project 或权限步骤时，明确告诉用户。
- 保持原始来源可追踪。
- 诚实标记不完整来源。
- 把摘要和完整来源分开。
- 把重复错题或笔记提取成可复用模型。
- 发现知识缺口时记录下来。
- 需要时加入间隔复习字段。
- 维护控制台和复习题单。
- 长文档尽量使用中英双文件结构。
- 优先做小而可审查的改动。
- 编辑后说明改了哪些文件。

## 不要做

- 不要编造缺失的学习上下文。
- 不要把摘要当作来源。
- 不要公开私人样例。
- 不要把受保护或私人学习材料放进公开仓库。
- 未明确要求时不要删除用户资料。
- 不要把长文档写成一句英文一句中文的混排。
- 不要为了仓库漂亮牺牲学习效果。
- 不要把 GitHub Actions 或 API key 作为基础部署要求。

## 新用户仓库搭建

帮助用户创建自己的学习仓库时：

1. 确认模板仓库和目标仓库。
2. 检查目标仓库是空仓库还是已有文件。
3. 确认仓库是公开还是私有。
4. 如果会存真实学习资料，建议使用私有仓库。
5. 在目标仓库复制或重建核心方法文件和模板。
6. 创建 `dashboard.md`。
7. 创建 `learner-profile.md`。
8. 创建 `goals/main-goal.md`。
9. 创建 sources、models、knowledge-gaps、reviews、templates、agents、automations、archive 等目录。
10. 加入 skill 运行层或记忆回退说明。
11. 询问用户第一个学习目标。
12. 汇报创建了什么。

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