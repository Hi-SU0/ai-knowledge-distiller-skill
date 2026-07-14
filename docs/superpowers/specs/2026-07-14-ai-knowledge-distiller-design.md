# AI Knowledge Distiller Skill Design

## Goal

Create a reusable repository-level Agent Skill named `ai-knowledge-distiller` for distilling AI videos, articles, courses, podcasts, papers, official documentation, and repositories into a source-traceable Obsidian knowledge base.

## Architecture

- Keep `.agents/skills/ai-knowledge-distiller/SKILL.md` concise and action-oriented.
- Move detailed vault structure, processing workflow, templates, and quality rules into one-level `references/` files.
- Store copy-ready Obsidian templates under `assets/obsidian-templates/`.
- Keep v0.1 instruction-only. `scripts/README.md` documents future automation boundaries without implementing download, scraping, ASR, or platform bypasses.
- Provide repository documentation in `README.md`, scenario specifications in `tests/`, and realistic notes in `examples/`.

## Repository Localization

- Use `README.md` as the default Chinese repository homepage.
- Add `README_EN.md` as the English homepage.
- Put prominent `[中文]` and `[English]` links at the top of both files to simulate a language switch within GitHub's Markdown limitations.
- Keep the executable Skill instructions single-sourced; do not maintain separate Chinese and English copies of `SKILL.md`.

## Processing Model

For each source, record provenance and material completeness before reconstructing its knowledge structure. Separate source statements, reasonable inference, creator opinion, external supplementation, unverified claims, and possibly outdated information. Update global concepts only after scanning names, aliases, abbreviations, and existing links.

## Safety and Preservation

- Never infer content from a title alone.
- Never treat unchecked automatic transcripts as authoritative.
- Never overwrite valid human edits or delete existing notes without explicit authorization.
- Never merge creator opinions into unattributed consensus.
- Stop unrestricted bulk processing; validate a small sample first and perform maintenance every five sources.

## Testing Strategy

1. Write at least eight scenario contracts before SKILL.md.
2. Cover missing subtitles, ASR errors, duplicate concepts, conflicting sources, oversized batches, and protected human notes.
3. Validate frontmatter, naming, relative links, required references, templates, directory structure, and privacy.
4. Run the official skill validator plus repository-specific structural checks.

## Delivery

Commit the completed project on `main` with `feat: create ai knowledge distiller skill`, push to the configured origin, and report the repository URL and commit SHA. Use Git credential management; never request or store a personal access token.
