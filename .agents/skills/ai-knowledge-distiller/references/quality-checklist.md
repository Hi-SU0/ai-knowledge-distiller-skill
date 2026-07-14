# Quality Checklist

Apply this checklist before completing a source, batch, migration, or vault-maintenance task.

## Source completeness

- [ ] The note states exactly which primary and supporting materials were accessed.
- [ ] Transcript, article, paper, documentation, visual, or code completeness is recorded.
- [ ] Missing chapters, visuals, attachments, pages, or code are identified.
- [ ] Completeness (`high`, `medium`, or `low`) matches the evidence.
- [ ] No claim is inferred from a title or thumbnail alone.

## Hallucination and transcript checks

- [ ] Automatic transcript names and technical terms were checked against context or primary sources.
- [ ] No invented timestamp, quotation, citation, identifier, metric, or visual detail appears.
- [ ] Short quotations are necessary, accurate, and limited.
- [ ] Uncertain material is labeled `暂未验证` instead of silently normalized.

## Concept deduplication

- [ ] Existing filenames, headings, aliases, abbreviations, Chinese names, and English names were searched.
- [ ] Equivalent concepts were merged into one canonical note.
- [ ] Distinct concepts with similar names explain their difference and link to each other.
- [ ] Different creators' explanations retain separate attribution inside the shared concept note.

## Links and paths

- [ ] Source notes are stored under the correct content type and creator or organization.
- [ ] Concepts, topic summaries, comparisons, and maps remain global.
- [ ] Filenames match wikilink targets and avoid invalid filesystem characters.
- [ ] Every new wikilink resolves, uses an alias, or is explicitly recorded as a knowledge gap.
- [ ] Moved files have repaired inbound and outbound links.

## Fact, inference, and viewpoint separation

- [ ] `来源明确陈述`, `合理推导`, `创作者个人观点`, and `外部补充` are visibly distinct.
- [ ] Creator opinions are attributed and not presented as industry consensus.
- [ ] External additions have their own source and do not alter the creator's original meaning.
- [ ] Conflicting sources are preserved and compared rather than silently reconciled.

## Staleness and verification

- [ ] Product, model, price, capability, API, version, company, and trend claims were checked for time sensitivity.
- [ ] Unsupported or disputed claims are in `暂未验证` or the pending-verification area.
- [ ] Time-sensitive claims are labeled `可能已经过时` with the checked date when applicable.
- [ ] Primary or official material is preferred for verification.

## Incremental editing and maintenance

- [ ] Existing files were read before modification.
- [ ] Valid human edits were preserved; conflicts are reported instead of overwritten.
- [ ] Knowledge maps, topic summaries, creator/source index, and processing record were updated as required.
- [ ] After five sources, duplicate, link, conflict, gap, and learning-order maintenance was performed.
- [ ] Created, modified, moved, merged, unresolved, and recommended-next files are reported.
