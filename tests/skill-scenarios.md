# Skill Scenario Tests

These scenario contracts define observable behavior for `ai-knowledge-distiller`. Each scenario must be satisfied by the Skill instructions and references.

## Scenario 1: Video with complete official subtitles

### Input task

“Distill this AI Agent video. The publisher provides complete subtitles, chapters, description, and source links.”

### Likely error without the Skill

The agent produces a transcript-style summary, drops timestamps, and does not separate reusable concepts from video-specific context.

### Required behavior

Prefer the official subtitles, reconstruct the knowledge structure, retain important timestamps, classify atomic knowledge and creator opinion, and update existing concept notes before creating new ones.

### Acceptance criteria

- Source note records title, creator, URL, publication date, duration, materials, subtitle completeness, processing date, and completeness.
- Important conclusions link to chapters or timestamps when available.
- “My understanding” is visibly separated from source content.

## Scenario 2: Video without subtitles, only title and description

### Input task

“Summarize this video. Only its title, short description, tags, and duration are available.”

### Likely error without the Skill

The agent fills missing content with generic domain knowledge or assumptions inferred from the title.

### Required behavior

Do not infer unseen arguments. Record the obtained materials, mark completeness as low or medium, distill only supported claims, and list missing subtitles, visuals, examples, and reasoning as unresolved.

### Acceptance criteria

- No unsupported claims are attributed to the creator.
- Missing materials are explicit.
- The note uses `暂未验证` or equivalent evidence labels for uncertain items.

## Scenario 3: Automatic transcript with many recognition errors

### Input task

“Use this ASR transcript containing inconsistent product names, broken sentences, and incorrect technical terms.”

### Likely error without the Skill

The agent copies recognition errors into definitions, filenames, tags, and wikilinks.

### Required behavior

Treat ASR as auxiliary evidence, cross-check terminology against the source page and authoritative references, preserve uncertainty when correction is not reliable, and never quote corrupted text as exact speech.

### Acceptance criteria

- Suspected ASR errors are corrected only with evidence or moved to verification notes.
- Concept names use stable canonical terminology.
- No long transcript passages are copied.

## Scenario 4: Two creators explain the same AI concept

### Input task

“Creator A and Creator B both explain RAG with different analogies and implementation preferences.”

### Likely error without the Skill

The agent creates separate `Creator A RAG.md` and `Creator B RAG.md` files or merges their claims without attribution.

### Required behavior

Update one global `RAG.md` concept note. Add separate source sections, then record shared ground, different definitions, analogies, technical routes, scenarios, conflicts, and freshness.

### Acceptance criteria

- Exactly one canonical RAG concept file exists.
- Each creator’s explanation retains a source link.
- Consensus and disagreement are separate sections.

## Scenario 5: An equivalent concept already exists under a synonym

### Input task

“Create a note for Context Window, but the vault already contains `Context.md` with aliases `Context Window` and `上下文窗口`.”

### Likely error without the Skill

The agent creates another concept file and introduces ambiguous links.

### Required behavior

Scan filenames, headings, aliases, Chinese names, English names, and abbreviations before creating a concept. Update `Context.md` when the semantic boundary matches; create a new file only when the concepts are genuinely different.

### Acceptance criteria

- No duplicate Context Window file is created.
- The existing note receives the new source explanation incrementally.
- Existing human content remains intact.

## Scenario 6: Creator opinion conflicts with official documentation

### Input task

“A creator says an API has no rate limit, while the current official documentation defines one.”

### Likely error without the Skill

The agent silently replaces one claim with the other or presents the creator’s statement as current fact.

### Required behavior

Preserve the creator statement as creator opinion or source statement with its publication date. Add the official documentation as external supplementation, mark the conflict and likely staleness, and do not rewrite history.

### Acceptance criteria

- Both claims retain attribution and dates.
- The current operational guidance points to the official documentation.
- The conflict appears in verification or viewpoint-comparison notes.

## Scenario 7: User requests processing 100 videos at once

### Input task

“Process all 100 videos immediately and do not stop for review.”

### Likely error without the Skill

The agent creates many low-confidence notes, duplicate concepts, and inconsistent taxonomy in one pass.

### Required behavior

Explain the quality risk, inventory the batch, select a small representative sample, and validate structure before expansion. Perform maintenance after every five processed sources.

### Acceptance criteria

- No unchecked 100-item write occurs.
- The first batch has explicit selection reasons and review gates.
- Maintenance covers duplicate concepts, links, maps, conflicts, gaps, and learning order.

## Scenario 8: User asks to overwrite a human-edited note

### Input task

“Replace the existing AI Agent note with the generated version; do not read the old file.”

### Likely error without the Skill

The agent destroys curated explanations, manual links, and corrections.

### Required behavior

Read the existing note first, preserve valid manual content, apply an incremental merge, and record corrections or unresolved conflicts. Request explicit authorization before destructive replacement.

### Acceptance criteria

- Existing valid sections and links remain.
- Changes are incremental and traceable.
- No file is deleted or wholesale replaced without explicit authorization.

## Scenario 9: Time-sensitive model and product information

### Input task

“Record the video’s model context length, product commands, pricing, and API behavior as reusable facts.”

### Likely error without the Skill

The agent treats publication-date product details as timeless facts.

### Required behavior

Retain the video claim with its date, mark version-sensitive details as `可能已经过时`, and verify against current first-party documentation when current guidance is required.

### Acceptance criteria

- Version, date, and source are recorded.
- Current and historical claims are not conflated.
- Unverified numbers remain in the verification queue.

## Scenario 10: A write introduces broken Obsidian links

### Input task

“Rename a concept and reorganize source-note folders while preserving the vault.”

### Likely error without the Skill

The agent moves files but leaves stale wikilinks, duplicate basenames, or path-dependent links.

### Required behavior

Inventory incoming and outgoing links, avoid overwriting target files, update affected indexes, validate wikilink targets, and record migration operations.

### Acceptance criteria

- No unresolved wikilink is introduced.
- Duplicate basenames are identified before the move.
- Migration mapping and modified files are recorded.
