# Demo：中考数学轻量学习闭环

这是虚构示例，用来展示 GitLearnOS 如何从一次真实作答形成可检查的学习状态。它不包含真实学校、老师或个人信息。

## 主目标

```text
在 30 天内提升中考数学几何模型识别能力。
```

## 这次会话发生了什么

```text
虚构来源记录
→ 学习者先做识别题
→ 能想到相似三角形，但对应关系错误
→ 记录 recognition 类型知识缺口
→ 给予关键提示
→ 变式题在提示后正确
→ 证据评分 1
→ 两天后再次复习
```

注意：AI 已经讲过，不代表学习者掌握。因为本次需要关键提示，所以模型保持 `learning`，知识缺口保持 `active`。

## 文件

```text
goals/main-goal.md
learner-profile.md
sources/fictional-geometry-source.md
models/geometry-similarity-model.md
knowledge-gaps/similarity-correspondence-gap.md
reviews/2026-07-03_practice-set.md
sessions/2026-07-03_similarity-session.md
dashboard.md
```

## 这个 demo 证明什么

GitLearnOS 不只是把一道题整理成漂亮笔记。它保存：

- 来源到底是否完整；
- 学习者第一次独立做出了什么；
- 错误属于哪一种缺口；
- Agent 使用了多少提示；
- 为什么得到这个分数；
- 哪些状态因此改变；
- 下一次应该怎么检验。
