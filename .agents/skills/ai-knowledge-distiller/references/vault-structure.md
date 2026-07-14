# AI Knowledge Vault Structure

## Canonical structure

```text
AI知识库/
├─ 00-AI知识地图/
│  ├─ AI知识总览.md
│  ├─ AI学习路线.md
│  ├─ 主题索引.md
│  └─ 来源与创作者索引.md
├─ 01-来源笔记/
│  ├─ 视频/<创作者>/
│  ├─ 文章/<创作者或机构>/
│  ├─ 课程/<创作者或机构>/
│  ├─ 播客/<创作者或节目>/
│  ├─ 论文/<作者或机构>/
│  ├─ 官方文档/<组织或项目>/
│  └─ GitHub项目/<组织或作者>/
├─ 02-原子概念/
├─ 03-主题综述/
├─ 04-观点对比/
├─ 05-案例与类比/
├─ 06-实践项目/
├─ 07-代码与工具/
├─ 08-待验证内容/
├─ 09-学习记录/
└─ 99-系统维护/
```

## Directory purposes

- `00-AI知识地图`: global navigation, learning routes, topic index, and source/creator index.
- `01-来源笔记`: source-specific notes classified first by content type and then by creator or organization.
- `02-原子概念`: globally shared reusable concepts; never split by creator.
- `03-主题综述`: cross-source synthesis centered on an AI topic.
- `04-观点对比`: agreements, different definitions, routes, scenarios, conflicts, and staleness across sources.
- `05-案例与类比`: reusable demonstrations, analogies, and case studies with attribution.
- `06-实践项目`: executable exercises, projects, milestones, and acceptance criteria.
- `07-代码与工具`: code patterns, tool notes, version constraints, and official references.
- `08-待验证内容`: unsupported, disputed, or time-sensitive claims awaiting verification.
- `09-学习记录`: personal progress, review logs, and spaced-repetition notes.
- `99-系统维护`: processing logs, migrations, duplicate audits, link checks, and maintenance reports.

## Naming rules

- Source note: `YYYY-MM-DD 标题.md`; use the publication date when known and `日期未知` when it is not.
- Concept note: canonical standard name, for example `AI Agent.md`; store Chinese, English, abbreviations, and variants in `aliases`.
- Topic summary: a stable topic-oriented name such as `Agent完整知识体系.md`.
- Comparison note: `主题 - 来源A与来源B观点对比.md` or a broader stable comparison name.
- Maintenance record: `YYYY-MM-DD 操作类型.md`.
- Use UTF-8 Markdown. Avoid characters invalid on common filesystems and keep link targets identical to filenames.

## Required global map files

Maintain these files continuously:

- `00-AI知识地图/AI知识总览.md`
- `00-AI知识地图/AI学习路线.md`
- `00-AI知识地图/主题索引.md`
- `00-AI知识地图/来源与创作者索引.md`

The creator index records name, homepage, primary platform, focus, difficulty, audience, processed and pending sources, representative sources, and complementarity with other creators.

## Migration rules

1. Inventory and read the old vault before moving anything.
2. Map old video notes into `01-来源笔记/视频/<创作者>/` and other source types into their corresponding folders.
3. Move old concepts into the global `02-原子概念` directory only after checking names and aliases.
4. Merge duplicate concepts incrementally. Preserve unique explanations and their provenance.
5. Do not overwrite human-edited notes. When two files conflict, retain both, mark the conflict, and request review.
6. Repair affected wikilinks and indexes after moves. Check both filenames and aliases.
7. Record every move, merge, rename, unresolved conflict, and link repair under `99-系统维护`.
8. Do not delete effective content without explicit authorization.

## Legacy mapping

| Legacy location | New location |
| --- | --- |
| `博主知识库/00-知识地图` | `AI知识库/00-AI知识地图` |
| `博主知识库/01-视频笔记` | `AI知识库/01-来源笔记/视频/<创作者>` |
| `博主知识库/02-原子概念` | `AI知识库/02-原子概念` |
| `博主知识库/03-主题综述` | `AI知识库/03-主题综述` |
| `博主知识库/04-案例与类比` | `AI知识库/05-案例与类比` |
| `博主知识库/05-实践项目` | `AI知识库/06-实践项目` |
| `博主知识库/06-待验证内容` | `AI知识库/08-待验证内容` |
| `博主知识库/07-索引与标签` | split into global maps, topic index, and creator index |
| `博主知识库/99-处理记录` | `AI知识库/99-系统维护` |
