# AI Knowledge Distiller Skill

[中文](README.md) | [English](README_EN.md)

一个用于将 AI 领域的视频、文章、课程、播客、论文、官方文档和 GitHub 项目蒸馏为结构化 Obsidian 知识库的可复用 Agent Skill。

它以知识主题为中心维护全局原子概念、主题综述、观点对比、知识地图和来源追溯，避免为不同创作者重复创建同一概念。

## 适用场景

- 把可靠的 AI 来源材料转化为结构化 Obsidian 笔记。
- 提取或增量更新全局原子概念。
- 融合多个来源，编写主题综述和学习路线。
- 比较不同创作者的定义、类比、技术路线和观点冲突。
- 审核来源完整度、过时信息、重复概念和失效双向链接。

## 项目结构

```text
ai-knowledge-distiller-skill/
├─ .agents/skills/ai-knowledge-distiller/
│  ├─ SKILL.md
│  ├─ references/
│  │  ├─ vault-structure.md
│  │  ├─ source-processing-workflow.md
│  │  ├─ source-note-template.md
│  │  ├─ concept-note-template.md
│  │  ├─ topic-summary-template.md
│  │  ├─ creator-index-template.md
│  │  └─ quality-checklist.md
│  ├─ assets/obsidian-templates/
│  └─ scripts/README.md
├─ tests/skill-scenarios.md
├─ examples/
├─ README.md
├─ README_EN.md
├─ LICENSE
└─ .gitignore
```

## 安装方法

### 作为仓库级 Skill 使用

将本仓库的 `.agents/skills/ai-knowledge-distiller` 保留在目标仓库中。Codex 在该仓库工作时可以发现并按任务触发它。

```powershell
git clone https://github.com/Hi-SU0/ai-knowledge-distiller-skill.git
```

也可以只把 `.agents/skills/ai-knowledge-distiller` 复制到已有项目的同名路径。

### 复制到用户级 Skill 目录

将 `.agents/skills/ai-knowledge-distiller` 整个目录复制到：

- Windows：`$HOME\.codex\skills\ai-knowledge-distiller`
- macOS / Linux：`~/.codex/skills/ai-knowledge-distiller`

重新打开 Codex 任务后即可使用。不同 Codex 版本的用户级目录约定可能变化，请以当前产品文档为准。

## 在 Codex 中调用

可以显式指定 Skill：

```text
请使用 $ai-knowledge-distiller，把这份 AI Agent 官方字幕蒸馏进我的 Obsidian Vault，并更新已有概念而不是创建重复文件。
```

也可以自然描述与其触发场景一致的任务，Codex 可根据 Skill 的 description 自动选择。

更多示例：

```text
使用 $ai-knowledge-distiller 对比这两位创作者对 MCP 的定义，保留各自出处，并更新全局 MCP 概念笔记。
```

```text
使用 $ai-knowledge-distiller 检查这个 AI 知识库中的重复概念、待验证内容和失效 Obsidian 链接，只输出安全的增量修改。
```

## 触发与不触发示例

适合触发：

- “蒸馏这篇 RAG 论文并更新我的全局概念卡片。”
- “把官方课程文字稿整理为来源笔记、主题综述和学习路线。”
- “比较两位创作者对 AI Agent 的观点差异。”

不适合触发：

- “下载 100 个 B 站视频并绕过平台限制。”
- “从这段音频自动生成字幕。”
- “只根据标题猜测这个视频讲了什么。”

## Obsidian Vault 配置

建议在 Vault 中建立 `AI知识库`，并采用 [知识库结构说明](.agents/skills/ai-knowledge-distiller/references/vault-structure.md) 中的全局目录。来源笔记按“内容类型 + 创作者或机构”存放；原子概念、主题综述、观点对比和知识地图全局共用。

可将 [Obsidian 模板目录](.agents/skills/ai-knowledge-distiller/assets/obsidian-templates/) 中的文件复制到 Vault 的模板文件夹，再在 Obsidian 的模板设置中选择该文件夹。

## 设计原则

- 不根据标题、封面或简介编造正文内容。
- 优先使用官方字幕、原始文章、原始论文、官方文档和仓库代码。
- 自动字幕必须校对后才能进入知识库。
- 明确区分来源陈述、合理推导、创作者观点和外部补充。
- 新建概念前扫描中文名、英文名、缩写和别名。
- 不覆盖有效的人工修改；信息不足时明确标记完整度和缺失材料。
- 先用少量样本验证流程，每处理五个来源执行一次维护。

## 当前限制

当前 `v0.1` 以指令型 Skill 为主：

- 尚未自动下载 B 站或 YouTube 视频。
- 尚未自动进行语音识别。
- 尚未提供批量字幕提取和知识库维护脚本。
- 获取不到字幕或原始内容时不得编造内容，只能处理可可靠验证的部分。

## 后续开发计划

- 增加非破坏性的 Vault 清单与维护报告工具。
- 增加用户提供字幕或官方导出字幕的导入器。
- 增加概念别名、重复候选和 Obsidian 链接检查器。
- 增加 Frontmatter、来源完整度和五来源维护周期验证。

任何自动化都应保留人工修改、默认只报告候选变更，并为移动、合并或删除提供明确记录。

## 测试

[场景测试](tests/skill-scenarios.md) 定义了完整字幕、无字幕、错误自动字幕、同义概念、来源冲突、大批量请求和人工笔记保护等行为契约。发布前还应检查 Skill Frontmatter、相对链接、模板格式、隐私信息和目录结构。

## License

[MIT License](LICENSE)
