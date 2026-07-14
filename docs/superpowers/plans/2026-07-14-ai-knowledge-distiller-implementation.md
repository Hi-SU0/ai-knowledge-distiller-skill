# AI Knowledge Distiller Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build and publish an instruction-only Agent Skill that distills AI sources into a source-traceable, globally deduplicated Obsidian knowledge base.

**Architecture:** Keep the runtime entrypoint concise at `.agents/skills/ai-knowledge-distiller/SKILL.md`. Route detailed directory rules, workflows, note schemas, and quality checks to one-level references; provide copy-ready templates, examples, scenario contracts, and bilingual repository documentation.

**Tech Stack:** Markdown, YAML frontmatter, Agent Skills specification, Obsidian wikilinks, Git, GitHub.

## Global Constraints

- Use the exact skill name `ai-knowledge-distiller`.
- Keep v0.1 instruction-only; do not implement video downloading, platform bypasses, batch scraping, or ASR.
- Preserve source provenance, evidence completeness, human edits, and global concept identity.
- Use `README.md` for Chinese and `README_EN.md` for English, with reciprocal language links.
- Commit implementation with `feat: create ai knowledge distiller skill` and push `main`.

---

### Task 1: Define scenario and structural tests first

**Files:**
- Create: `tests/skill-scenarios.md`

**Interfaces:**
- Consumes: approved design specification.
- Produces: at least eight scenario contracts with input, baseline failure, required behavior, and acceptance criteria.

- [ ] **Step 1: Create the scenario contract before SKILL.md**

Cover official subtitles, missing subtitles, noisy ASR, duplicate cross-creator concepts, existing aliases, creator/official conflict, a 100-video bulk request, and protected human notes.

- [ ] **Step 2: Run the structural preflight and verify RED**

```powershell
$skill = '.agents/skills/ai-knowledge-distiller'
@('SKILL.md','references/vault-structure.md','references/quality-checklist.md') |
  ForEach-Object { if (-not (Test-Path (Join-Path $skill $_))) { "MISSING $_" } }
```

Expected: missing-file output because implementation has not been created.

### Task 2: Initialize the skill and reusable resources

**Files:**
- Create: `.agents/skills/ai-knowledge-distiller/SKILL.md`
- Create: `.agents/skills/ai-knowledge-distiller/references/*.md`
- Create: `.agents/skills/ai-knowledge-distiller/assets/obsidian-templates/*.md`
- Create: `.agents/skills/ai-knowledge-distiller/scripts/README.md`

**Interfaces:**
- Consumes: scenario contract from Task 1.
- Produces: one runtime skill entrypoint and all referenced rules/templates.

- [ ] **Step 1: Run the official initializer**

```powershell
python C:\Users\SUO\.codex\skills\.system\skill-creator\scripts\init_skill.py ai-knowledge-distiller --path .agents/skills --resources scripts,references,assets
```

- [ ] **Step 2: Write detailed references and assets**

Create the exact requested files. Put full directory rules in `vault-structure.md`, processing logic in `source-processing-workflow.md`, schemas in template references, and all gates in `quality-checklist.md`. Copy the three core Obsidian templates into assets.

- [ ] **Step 3: Write concise SKILL.md**

Use only `name` and `description` frontmatter fields. Keep the body imperative and route all detailed schemas to references.

### Task 3: Add examples and bilingual repository documentation

**Files:**
- Create: `examples/example-source-note.md`
- Create: `examples/example-concept-note.md`
- Modify: `README.md`
- Create: `README_EN.md`
- Modify: `.gitignore`

**Interfaces:**
- Consumes: final templates and skill behavior.
- Produces: copyable examples and GitHub-facing Chinese/English documentation.

- [ ] **Step 1: Create realistic examples**

Demonstrate source boundaries, evidence labels, aliases, global concept reuse, and Obsidian links without using private paths or credentials.

- [ ] **Step 2: Write reciprocal README language links**

Place `[中文](README.md) | [English](README_EN.md)` at the top of both files. Document installation, Codex invocation, user-level and repository-level setup, Vault configuration, limitations, and roadmap.

### Task 4: Validate and refactor

**Files:**
- Validate all repository Markdown and YAML files.

**Interfaces:**
- Consumes: completed repository.
- Produces: zero validation errors and a clean intended diff.

- [ ] **Step 1: Run official validator**

```powershell
python C:\Users\SUO\.codex\skills\.system\skill-creator\scripts\quick_validate.py .agents/skills/ai-knowledge-distiller
```

Expected: valid skill.

- [ ] **Step 2: Run repository checks**

Check skill name syntax, frontmatter, relative links, reference existence, template fields, exact directory tree, UTF-8 decoding, privacy patterns, and Git diff whitespace.

- [ ] **Step 3: Re-run until all checks pass**

Fix only defects revealed by checks; do not add download, scraping, or ASR functionality.

### Task 5: Commit and publish

**Files:**
- Stage all intended project files.

**Interfaces:**
- Consumes: validated repository.
- Produces: pushed `main` and final commit SHA.

- [ ] **Step 1: Inspect scope**

```powershell
git status -sb
git diff --check
git diff --stat
```

- [ ] **Step 2: Commit implementation**

```powershell
git add .agents tests examples README.md README_EN.md LICENSE .gitignore docs
git commit -m "feat: create ai knowledge distiller skill"
```

- [ ] **Step 3: Push main**

```powershell
git push origin main
```

- [ ] **Step 4: Report repository and SHA**

```powershell
git rev-parse HEAD
git status -sb
```
