# AI Knowledge Distiller Skill

[中文](README.md) | [English](README_EN.md)

A reusable Agent Skill for distilling AI videos, articles, courses, podcasts, papers, official documentation, and GitHub repositories into a structured Obsidian knowledge base.

It maintains globally shared atomic concepts, topic summaries, viewpoint comparisons, knowledge maps, and source provenance around knowledge topics rather than individual creators.

## When to use it

- Convert reliable AI source material into structured Obsidian notes.
- Create or incrementally update globally shared atomic concepts.
- Synthesize multiple sources into topic guides and learning paths.
- Compare creators' definitions, analogies, technical routes, and conflicts.
- Audit source completeness, stale claims, duplicate concepts, and broken wikilinks.

## Repository layout

```text
ai-knowledge-distiller-skill/
├─ .agents/skills/ai-knowledge-distiller/
│  ├─ SKILL.md
│  ├─ references/
│  ├─ assets/obsidian-templates/
│  └─ scripts/README.md
├─ tests/skill-scenarios.md
├─ examples/
├─ README.md
├─ README_EN.md
├─ LICENSE
└─ .gitignore
```

## Installation

### Repository-level Skill

Keep `.agents/skills/ai-knowledge-distiller` in the target repository. Codex can discover it while working in that repository.

```powershell
git clone https://github.com/Hi-SU0/ai-knowledge-distiller-skill.git
```

You may also copy only `.agents/skills/ai-knowledge-distiller` into the same path in an existing project.

### User-level Skill

Copy `.agents/skills/ai-knowledge-distiller` to:

- Windows: `$HOME\.codex\skills\ai-knowledge-distiller`
- macOS / Linux: `~/.codex/skills/ai-knowledge-distiller`

Open a new Codex task after copying it. User-level locations can vary by Codex version, so consult current product documentation when needed.

## Using it in Codex

Explicit invocation:

```text
Use $ai-knowledge-distiller to distill this official AI Agent transcript into my Obsidian vault, updating existing concepts instead of creating duplicates.
```

Codex may also select the Skill automatically when a natural-language request matches its description.

More examples:

```text
Use $ai-knowledge-distiller to compare how these two creators define MCP, preserve attribution, and update the global MCP concept note.
```

```text
Use $ai-knowledge-distiller to audit this AI vault for duplicate concepts, unverified claims, and broken Obsidian links. Make only safe incremental edits.
```

## Trigger and non-trigger examples

Good matches:

- “Distill this RAG paper and update my global concept cards.”
- “Turn this official course transcript into source notes, a topic summary, and a learning path.”
- “Compare two creators' views of AI agents.”

Not supported by v0.1:

- “Download 100 Bilibili videos and bypass platform restrictions.”
- “Generate a transcript automatically from this audio.”
- “Guess what this video contains from its title.”

## Obsidian Vault setup

Create an `AI知识库` root and follow the [vault structure reference](.agents/skills/ai-knowledge-distiller/references/vault-structure.md). Store source notes by content type and creator or organization. Keep atomic concepts, topic summaries, comparisons, and maps global.

You can copy files from the [Obsidian templates directory](.agents/skills/ai-knowledge-distiller/assets/obsidian-templates/) into your Vault's template folder and select that folder in Obsidian's Templates settings.

## Core principles

- Never invent content from a title, thumbnail, or description.
- Prefer official transcripts, original articles and papers, official documentation, and repository code.
- Review automatic transcripts before using them.
- Separate source statements, reasonable inferences, creator opinions, and external supplements.
- Search Chinese names, English names, abbreviations, and aliases before creating a concept.
- Preserve valid human edits and state completeness and missing evidence.
- Validate the workflow on a small sample and run maintenance after every five sources.

## Current limitations

Version `v0.1` is instruction-driven:

- It does not automatically download Bilibili or YouTube videos.
- It does not perform automatic speech recognition.
- It does not yet provide bulk transcript extraction or vault-maintenance scripts.
- It must not fabricate content when subtitles or primary material are unavailable.

## Roadmap

- Non-destructive vault inventory and maintenance reports.
- Import of user-provided or officially exported transcripts.
- Concept alias, duplicate-candidate, and wikilink checkers.
- Frontmatter, completeness, and five-source maintenance validators.

Automation should preserve human edits, report candidate changes by default, and log every move, merge, or deletion.

## Tests

[Scenario contracts](tests/skill-scenarios.md) cover complete and missing transcripts, noisy ASR, synonym concepts, source conflicts, oversized batch requests, and protection of human notes. Release validation also checks frontmatter, relative links, templates, privacy, and the expected directory tree.

## License

[MIT License](LICENSE)
