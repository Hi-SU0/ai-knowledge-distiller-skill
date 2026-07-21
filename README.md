<p align="center">
  <img src="assets/readme/hero.svg" alt="AI Knowledge Distiller：把可靠 AI 来源转化为可追溯、去重且可持续维护的 Obsidian 知识网络" width="100%">
</p>

[中文](README.md) | [English](README_EN.md)

把可靠的 AI 来源变成可追溯、可复用、可维护的 Obsidian 知识网络：保留每个来源的语义与证据，同时持续更新全局共享知识。

## 先看格式证明

<p align="center">
  <img src="assets/readme/proof.svg" alt="两种互补输出：可追溯的来源笔记与跨来源更新的全局概念笔记" width="100%">
</p>

[查看来源笔记格式示例](examples/example-source-note.md) · [查看全局概念笔记格式示例](examples/example-concept-note.md)

这两个示例使用虚构来源材料演示格式和行为，不代表生产环境结果。可靠材料先成为带完整度、证据标签和定位信息的来源笔记，再更新全局共享的概念、主题、对比与知识地图，而不是为每位创作者复制一套知识。

## 为什么它不同

- 来源层保留“谁说了什么、材料是否完整、证据在哪里”；知识层只承载可复用的全局结构。
- 同一概念在不同来源中的解释进入同一份规范笔记，仍按来源分别保留共识、差异、观点和时效性。
- 新内容以增量方式进入已有 Vault：先读取现状，再更新相关笔记、索引和链接。

## 工作流程

<p align="center">
  <img src="assets/readme/workflow.svg" alt="五步知识蒸馏流程：获取来源、核验证据、重构知识、全局去重、持续维护" width="100%">
</p>

1. **SOURCE · 获取来源**：优先使用官方字幕、原始文章或论文、官方文档和仓库代码。
2. **VERIFY · 核验证据**：记录已取得与缺失的材料、完整度、定位信息和待验证内容。
3. **RESTRUCTURE · 重构知识**：重建问题、受众、论证、案例和结论，而不是逐行压缩文字稿。
4. **DEDUPLICATE · 全局去重**：复用规范概念，避免按创作者、语言或缩写建立知识孤岛。
5. **MAINTAIN · 持续维护**：修复链接、刷新地图与综述，并记录冲突、缺口和学习顺序。

## 快速开始

### 仓库级 Skill

最短路径是克隆仓库；Skill 位于 `.agents/skills/ai-knowledge-distiller`，Codex 在该仓库工作时可以发现它。

```powershell
git clone https://github.com/Hi-SU0/ai-knowledge-distiller-skill.git
```

也可以只把 `.agents/skills/ai-knowledge-distiller` 复制到已有项目的同名路径。

### 用户级 Skill

将 `.agents/skills/ai-knowledge-distiller` 整个目录复制到：

- Windows：`$HOME\.codex\skills\ai-knowledge-distiller`
- macOS / Linux：`~/.codex/skills/ai-knowledge-distiller`

复制后请打开一个新的 Codex 任务。用户级目录可能随 Codex 版本变化，请以当前产品文档为准。

### 首次调用

```text
请使用 $ai-knowledge-distiller，把这份 AI Agent 官方文字稿蒸馏进我的 Obsidian Vault：保留来源与证据，更新已有概念、主题和对比笔记，而不是创建重复文件。
```

## 安全源于设计

- **来源完整度**：明确记录取得了什么、缺少什么；材料不足时只处理可可靠验证的部分，不补写缺失正文。
- **证据与追溯**：区分来源明确陈述、合理推导、创作者个人观点、外部补充、暂未验证和可能已经过时，并尽量保留链接、日期、章节、页码或时间戳。
- **自动文字稿安全**：用户提供的 ASR/自动文字稿只作为辅助证据；须对照来源页面与权威资料核验术语，无法可靠纠正时保留不确定性，绝不把损坏文本当作逐字原话引用。
- **全局别名扫描**：新建概念前检查中文名、英文名、缩写、拼写变体和别名，语义相同则更新规范笔记。
- **人工编辑保护**：先读取已有笔记，保留有效人工内容并增量合并；未经明确授权不覆盖或删除。
- **小样本与五来源维护**：批量处理前先验证少量代表性样本；每处理五个来源，执行去重、链接、地图、综述、冲突、缺口和学习顺序维护。

## 限制与适用范围

### 适合的任务

- 蒸馏可靠的 AI 视频文字稿、文章、课程、播客文字稿、论文、官方文档或代码仓库。
- 创建或更新来源笔记、原子概念、主题综述、观点对比、创作者索引和知识地图。
- 审核重复概念、过时声明、来源缺失和失效 Wiki 链接。

它不适合不需要 AI 知识蒸馏或来源管理的普通笔记排版，也不用于绕过平台限制、受保护媒体下载或大规模抓取。

### v0.1 的当前限制

`v0.1` 是指令驱动的 Skill：

- 不会自动下载 Bilibili 或 YouTube 媒体。
- 不执行自动语音识别（ASR）。
- 不提供批量文字稿提取或 Vault 维护脚本。
- 获取不到字幕或原始内容时不得编造，只能处理可可靠验证的部分。

## 仓库导航

<details>
<summary>查看紧凑目录与关键文档</summary>

```text
ai-knowledge-distiller-skill/
├─ .agents/skills/ai-knowledge-distiller/
│  ├─ SKILL.md
│  ├─ references/
│  └─ assets/obsidian-templates/
├─ assets/readme/
├─ examples/
├─ tests/skill-scenarios.md
├─ README.md
└─ README_EN.md
```

- [Skill 行为说明](.agents/skills/ai-knowledge-distiller/SKILL.md)
- [Vault 结构、命名与迁移规则](.agents/skills/ai-knowledge-distiller/references/vault-structure.md)
- [来源笔记示例](examples/example-source-note.md) 与 [全局概念笔记示例](examples/example-concept-note.md)
- [Obsidian 模板目录](.agents/skills/ai-knowledge-distiller/assets/obsidian-templates/)
- [场景测试](tests/skill-scenarios.md)

</details>

## 路线图

- 非破坏性的 Vault 清单与维护报告。
- 用户提供或官方导出的文字稿导入器。
- 概念别名、重复候选和 Wiki 链接检查器。
- Frontmatter、来源完整度和五来源维护周期验证器。

未来自动化仍应保护人工编辑、默认报告候选变更，并记录每次移动、合并或删除。

## License

[MIT License](LICENSE)
