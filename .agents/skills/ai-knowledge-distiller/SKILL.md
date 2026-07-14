---
name: ai-knowledge-distiller
description: Use when distilling AI-related videos, articles, courses, podcasts, papers, documentation, or repositories into a structured Obsidian knowledge base.
---

# AI Knowledge Distiller

## Core goal

Turn reliable AI source material into a traceable, reusable, and maintainable Obsidian knowledge network. Preserve each source's meaning while maintaining globally shared concepts, topic summaries, comparisons, and learning paths.

## Use this skill for

- Distilling AI videos, articles, courses, podcasts, papers, official documentation, or repositories.
- Creating or updating source notes, atomic concepts, topic summaries, creator indexes, comparisons, and knowledge maps.
- Reconciling explanations of the same concept across sources without losing attribution.
- Auditing an AI knowledge vault for duplicates, stale claims, missing provenance, or broken wikilinks.

## Do not use this skill for

- Guessing content from a title, thumbnail, or short description.
- Downloading protected media, bypassing platform restrictions, bulk crawling, or performing speech recognition.
- General note formatting that does not require AI knowledge distillation or provenance management.

## Process one source

1. Inspect the target vault and existing notes before writing. Preserve valid human edits.
2. Acquire material in the priority order defined in [source-processing-workflow.md](references/source-processing-workflow.md). Record exactly what was and was not obtained.
3. Establish source metadata, completeness, missing material, and evidence quality.
4. Reconstruct the source's question, audience, prerequisites, structure, argument, examples, and conclusion. Do not compress a transcript line by line.
5. Separate reusable atomic knowledge, source-specific context, and creator opinions.
6. Scan existing concepts before creating any concept note. Update relevant topic summaries, comparisons, maps, and indexes.
7. Verify unstable or disputed claims. Keep external verification separate from the source's original meaning.
8. Write incrementally, check links and paths, then record all created and modified files.

Use a small representative sample before any batch. After every five processed sources, perform vault maintenance: merge duplicates, repair links, refresh maps and summaries, inspect conflicts, list gaps, and reconsider the learning order.

## Global concept deduplication

Before creating a concept, scan global concept notes for its Chinese name, English name, abbreviation, spelling variants, and aliases. Treat equivalent names as one concept and add aliases to the canonical note. Different creators explaining the same concept must update the same concept file under the global concept directory. Never isolate atomic concepts, topic summaries, or knowledge maps by creator.

## Source traceability

For each important claim, retain as much of the following as the material supports: source link, creator or organization, publication date, source identifier, chapter, page, section, or timestamp. Never invent timestamps, quotations, identifiers, or citations. Mark incomplete material and state what may be missing.

## Obsidian links

Use `[[Canonical Concept]]` only when the relationship aids navigation or understanding. Prefer canonical filenames and aliases; do not create links merely to increase link count. Source notes belong under content type and creator, while concepts, topic summaries, comparisons, and maps are globally shared. Verify that every newly introduced wikilink resolves or is intentionally listed as a knowledge gap.

## Evidence labels

Keep these categories visibly separate:

- `来源明确陈述`: directly supported by the source.
- `合理推导`: a conclusion derived from the source; state the reasoning.
- `创作者个人观点`: experience, judgment, preference, or prediction attributed to its creator.
- `外部补充`: information from another named source.
- `暂未验证`: a claim that lacks sufficient evidence.
- `可能已经过时`: time-sensitive information needing current verification.

If creator opinion conflicts with official or primary material, preserve both with attribution and explain the conflict. Do not silently replace either one.

## Required references

Read the files needed for the task before editing:

- For vault layout, naming, or migration: [vault-structure.md](references/vault-structure.md)
- For any source distillation: [source-processing-workflow.md](references/source-processing-workflow.md)
- For source notes: [source-note-template.md](references/source-note-template.md)
- For concepts: [concept-note-template.md](references/concept-note-template.md)
- For topic synthesis: [topic-summary-template.md](references/topic-summary-template.md)
- For creator/source indexes: [creator-index-template.md](references/creator-index-template.md)
- Before completion: [quality-checklist.md](references/quality-checklist.md)

## Completion check

Before reporting completion, apply the full quality checklist. At minimum verify source completeness, hallucination risk, concept duplication, evidence labels, stale claims, file paths, filenames, frontmatter, and newly added wikilinks. Report created files, updated files, uncertain information, and the next recommended source or maintenance action.

## Prohibited actions

- Do not infer source content from titles or metadata alone.
- Do not write unchecked automatic transcripts into the vault.
- Do not present creator opinions or model-generated inferences as consensus facts.
- Do not mix external supplements into a creator's original viewpoint.
- Do not duplicate concepts by creator, language, or abbreviation.
- Do not overwrite valid human-authored content or delete files without explicit authorization.
- Do not fabricate timestamps, quotations, citations, data, or source access.
- Do not process a large backlog before a small sample validates the structure.
