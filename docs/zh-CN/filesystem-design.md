# 文件系统设计

Repo as Review OS 应该把文件系统本身当作界面。

AI 不应该只写正文，还应该利用目录、文件名、日期、状态标签、索引和归档，让仓库一打开就能读出结构。

## 核心原则

好的文件树应该让人类和 AI 快速知道：

- 什么正在进行；
- 什么已经归档；
- 什么是来源；
- 什么是模型；
- 什么需要复习；
- 什么需要用户补充。

## 推荐结构

```text
review-os/
├── dashboard.md
├── inbox/
├── sources/
├── models/
├── reviews/
├── templates/
├── agents/
├── automations/
└── archive/
```

## 目录用途

- `inbox/`：等待处理的新材料。
- `sources/`：来源记录和引用。
- `models/`：可复用规律。
- `reviews/`：题单和复盘记录。
- `templates/`：模板。
- `agents/`：AI 接手规则。
- `automations/`：定时输出和日志。
- `archive/`：旧内容。

## 命名规则

文件名应该带有时间、主题和状态：

```text
YYYY-MM-DD_topic_status.md
```

## AI 行为

添加文件前，AI 应该先判断：

1. 它属于哪个目录？
2. 它是来源、摘要、模型、索引还是待补？
3. 是否需要更新控制台？
4. 是否应该归档旧内容？

## 实用规则

文件树本身就是产品的一部分。保持它清楚，让新的 AI 不用读完每个文件，也能理解系统。
