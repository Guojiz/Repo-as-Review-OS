# DeepTutor 多 Agent 参考

本页记录 GitLearnOS 应该从 DeepTutor 多 Agent 模式里借鉴什么。

参考仓库：

```text
https://github.com/HKUDS/DeepTutor
```

这是外部设计参考，不是 GitLearnOS 的产品身份。GitLearnOS 仍然来自原始 `zhongkao` 学习仓库模式，并继续把 GitHub / 本地 git 作为可检查的学习状态层。

## 应该借鉴什么

DeepTutor 有价值的模式不是“创建很多 Agent 然后让它们都写状态”。

真正有价值的是：

```text
主 chat / tutor loop
→ 需要时咨询一个聚焦子 Agent
→ 展示或记录子 Agent 的运行过程
→ 回到主 loop
→ 主 loop 用自己的口吻回答
→ 长期状态只在一个受控位置写入
```

DeepTutor 的默认 Chat surface 可以在一个 turn 里调用工具、基于知识库 grounding、读取附件、写 notebook 记录，并在合适上下文中咨询 subagent。它的 README 里把 `rag`、`read_source`、`read_memory`、`write_memory`、`read_skill`、`load_tools`、`exec`、`ask_user`、`write_note`、`github` 和 `consult_subagent` 等描述为根据上下文挂载的工具。

DeepTutor 的 `consult_subagent` 工具也是一个很好的边界模型。模型只提供聚焦的 `question`；backend、工作目录、配置、预算和 session state 由服务端注入。被咨询的 Agent 展示自己的运行过程，返回最终答案；主模型在咨询预算用完后必须停止调用。

DeepTutor 的 subagent capability 还说明：咨询有 turn-scoped budget，被咨询 Agent 的 session 可以跨多次咨询延续，主模型最后应该用自己的口吻回答用户，而不是冒充 subagent。

## GitLearnOS 的改造方式

对 GitLearnOS 来说，OpenHanako 多 Agent 应该使用**咨询模式**，而不是无控制并行写入。

推荐 OpenHanako 形态：

```text
GitLearnOS Maintainer
→ 主 loop
→ 负责 dashboard、learner-profile.md、索引、接手记录和最终写入

Source & Model Extractor
→ 在需要处理来源材料、错题、论文、截图或本地摘录时被咨询
→ 提出来源记录、可复用模型和知识缺口

Practice & Review Coach
→ 在需要复习题单、小测、间隔复习或下一步行动时被咨询
→ 提出练习和复习更新

Critic
→ 可选审查者
→ 审查模糊笔记、无来源断言、过期缺口、弱题目和学习画像漂移
```

## 最终写入者规则

默认只有 Maintainer 写入长期状态。

其他 Agent 可以：

```text
检查
提出建议
提取模型
总结
出题
审查
```

它们不应该独立重写 `learner-profile.md`、`dashboard.md`、`reviews/` 或 `knowledge-gaps/`，除非 Maintainer 明确委派写入并随后核对结果。

## 咨询预算规则

借鉴 DeepTutor 的 budget 思路：

```text
一次用户请求
→ 少量 subagent 咨询
→ 停止咨询
→ Maintainer 写入或汇报最终结果
```

推荐默认：

```text
普通任务：0-1 次咨询
来源较重任务：1-2 次咨询
复杂仓库修复：2-3 次咨询
```

超过这个范围，通常说明系统开始漂移，应该询问学习者或写接手记录。

## 自包含问题规则

每次咨询 subagent 都应该自包含：

```text
任务：
上下文：
允许读取的文件或来源：
输出格式：
写入权限：
停止条件：
```

除非运行时明确传递完整上下文，否则不要假设 subagent 能看到父对话。

## 口吻规则

最终回答属于 Maintainer 或当前主运行层。

不要用 subagent 的身份回答。不要用 subagent 的第一人称说话。应该总结 subagent 找到了什么，再由主运行层做最终判断。

## 状态规则

学习状态层仍然是：

```text
GitHub 目标仓库
或本地 git
或本地 git + Obsidian
```

DeepTutor 可以启发 Agent 咨询形态，但 GitLearnOS 状态仍然是文件化、可检查的。

## 不要复制什么

不要把 DeepTutor 的完整平台范围搬进 GitLearnOS 文档。

不要要求：

```text
完整 DeepTutor 安装
多用户部署
Knowledge Center / RAG engine stack
DeepTutor 三层记忆系统
partner workspace system
DeepTutor CLI
DeepTutor web app
```

这些是 DeepTutor 平台功能。GitLearnOS 只借鉴受控的多 Agent 咨询模式。
