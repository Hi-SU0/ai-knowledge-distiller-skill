# Source Note Template

Use this template for videos, articles, courses, podcasts, papers, official documentation, and repositories. Omit non-applicable optional fields rather than inventing values.

```markdown
---
type: source-note
source_type: video
creator:
organization:
title:
source:
source_id:
platform:
published:
duration:
processed:
completeness: medium
materials:
  - official-transcript
status: distilled
topics: []
tags:
  - 来源笔记
---

# 标题

## 一句话摘要

## 来源要解决的问题

## 目标受众与前置知识

## 内容地图

## 核心结论

## 论证与讲解过程

## 关键概念

## 案例、类比与关键画面

## 实践方法

## 容易误解的地方

## 创作者观点

## 我的理解

## 待验证内容

## 延伸问题

## 关联笔记

## 来源与处理说明
```

## Field rules

- `source_type`: one of `video`, `article`, `course`, `podcast`, `paper`, `documentation`, or `repository`.
- `creator`: a person or channel; use `organization` for institutional sources.
- `source`: canonical original URL, DOI, or repository URL.
- `source_id`: BV number, video ID, DOI, course ID, document version, or repository identifier when available.
- `published`: original publication date; do not substitute the processing date.
- `duration`: use for time-based media; a page count or version may be described in processing notes for other sources.
- `processed`: current processing date.
- `completeness`: `high`, `medium`, or `low`, justified in the final section.
- `materials`: list only material actually accessed, such as `official-transcript`, `source-page`, `slides`, `automatic-transcript`, `paper`, `documentation`, or `repository-code`.
- `topics`: YAML list of global topics.
- Put timestamps, page numbers, sections, or commit references beside claims when available.
- Keep `创作者观点`, `我的理解`, and external supplements separate from source-supported content.
