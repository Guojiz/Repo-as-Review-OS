---
name: repo-as-review-os-maintenance
description: Audit and repair a GitLearnOS target repository for stale dashboards, broken links, missing evidence, unsupported mastery claims, overdue reviews, duplicated state, and unclear source boundaries.
---

# GitLearnOS Maintenance

## Audit order

1. active goal;
2. dashboard freshness and links;
3. learner-profile claims and evidence;
4. active knowledge gaps;
5. due and unscored reviews;
6. model/source links;
7. stale, duplicated, or orphaned files.

## High-value checks

- dashboard duplicates state instead of linking it;
- an item is marked stable without independent evidence;
- a generated review has no learner result but appears complete;
- a profile claim has no evidence link or is based on one ambiguous event;
- a source record overstates access or completeness;
- next-review dates are missing, overdue, or inconsistent with the score;
- a goal has no concrete next action;
- an agent must read too many files to resume work;
- empty scaffolding outweighs actual learning state.

## Direct repair

Fix clear, low-risk issues directly: links, stale dashboard views, missing status fields, deterministic next dates, and obvious contradictions supported by files.

Ask before deletion, large restructuring, rewriting personal notes, changing strategy, publishing, visibility changes, secrets, or license changes.

## Output

```text
Repository health:
Evidence issues:
Changed files:
Unresolved decisions:
Next learning action:
```
