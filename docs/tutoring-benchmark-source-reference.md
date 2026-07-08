# Tutoring Benchmark Source Reference

This file records public benchmark-design ingredients that are useful for checking whether a learning repository has enough source variety, learner-state structure, and practice-task coverage.

It is a reference list, not a dependency and not bundled source material.

## Source inventory example

The DeepTutor technical report lists a TutorBench PDF source inventory. The list is useful as a reference for building a broad starter knowledge map.

### Textbook-derived PDFs

All listed textbook PDFs are sourced from OpenStax.

| English source | 中文参考名 | Splits listed in the report |
|---|---|---|
| Calculus Volume 2 | 微积分第 2 卷 | Chapters 1–2, 3–4, 5–6 |
| Calculus Volume 3 | 微积分第 3 卷 | Chapters 1–2, 3–4, 5–6 |
| Principles of Economics 3e | 经济学原理第 3 版 | Chapters 1–6, 7–12, 13–18 |
| Foundations of Information Systems | 信息系统基础 | Chapters 1–3, 4–6, 7–9 |
| Introduction to Computer Science | 计算机科学导论 | Chapters 1–3, 4–6, 7–9 |
| Introduction to Philosophy | 哲学导论 | Chapters 1–4, 5–8, 9–12 |
| Introduction to Business | 商业导论 | Chapters 1–5, 6–10, 11–15 |
| Writing Guide with Handbook | 写作指南与手册 | Chapters 1–6, 7–12, 13–18 |

### Paper-derived PDFs

| English source | 中文参考名 |
|---|---|
| Memory in the Age of AI Agents | AI Agent 时代的记忆 |
| DeepSeek-R1 incentivizes reasoning in LLMs through reinforcement learning | DeepSeek-R1：通过强化学习激励大模型推理 |
| LiveCodeBench: Holistic and Contamination Free Evaluation of Large Language Models for Code | LiveCodeBench：面向代码大模型的整体、无污染评测 |
| OpenVLA: An Open-Source Vision-Language-Action Model | OpenVLA：开源视觉-语言-动作模型 |
| Towards Reasoning Era: A Survey of Long Chain-of-Thought for Reasoning Large Language Models | 迈向推理时代：长思维链推理大模型综述 |
| YOLOv9: Learning What You Want to Learn Using Programmable Gradient Information | YOLOv9：使用可编程梯度信息学习想学内容 |

## Profile and task structure

A useful personalized tutoring benchmark does not only store source files.

It should connect:

```text
source material
→ learner profile
→ knowledge gaps
→ task type
→ initial learner request
→ expected gap exposure
→ success criteria
→ difficulty
```

For Repo as Review OS, the lightweight equivalent is:

```text
sources/
→ learner-profile.md
→ models/
→ reviews/
→ automations/practice-generator/
→ dashboard.md
```

## Task type coverage

The report lists four task types with sampling weights:

| Task type | 中文名 | Weight |
|---|---|---|
| Concept understanding | 概念理解 | 30% |
| Problem solving | 解题 | 30% |
| Application | 应用 | 20% |
| Comparison | 比较 | 20% |

A Repo as Review OS practice generator can reuse this distribution as a default, then adapt it to the learner profile.

## Rejection checks

The report describes three rejection checks for generated tasks:

1. Gap coherence: targeted gaps should form a coherent learning topic.
2. Task-gap fit: the task should naturally expose the targeted gaps.
3. Conversational naturalness and consistency: the task should read like a plausible learner request and not contain internal contradictions.

For Repo as Review OS, the Organizer + Critic + Revision routine should apply the same spirit:

```text
Is this practice linked to a real weak point?
Is it grounded in a source or model?
Is the task natural and useful?
Is the answer/explanation correct?
Should it be revised, approved, or rejected?
```

## Lightweight adaptation

Repo as Review OS does not need to reproduce the full benchmark machinery.

It can use the idea in a lighter way:

```text
recently split models
+ learner-profile.md
+ active weak points
+ source records
→ personalized practice ideas
→ critic revision
→ approved review set
→ spaced repetition / next review date
```

The important part is not the benchmark scale. The important part is the closed loop:

```text
source → model → weak point → personalized question → result → learner profile update → next review
```

## Attribution

This reference is based on the public DeepTutor technical report, arXiv:2604.26962, which lists the TutorBench PDF source inventory, task generation structure, and rejection checks. The material here is rewritten as a lightweight implementation reference for Repo as Review OS and does not bundle or redistribute the original PDFs.