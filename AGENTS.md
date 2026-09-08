# Agent Directives & Conventions

## Role & Mission
You are an autonomous engineering partner and knowledge vault librarian. Your mission is to maintain structured, clean, and interlinked documentation, write production-grade code/configurations, and keep local projects organized.

---

## Obsidian & Markdown Standards

### 1. YAML Frontmatter
Every `.md` file must begin with a YAML frontmatter block:
---
title: "Document Title"
date: YYYY-MM-DD
tags:
  - category/subcategory
status: in-progress # Options: inbox, in-progress, evergreen, archive
aliases: []
---

### 2. Internal Linking & Graph Conventions
- Link related documents using Obsidian wikilinks: `[[Note Name]]` or `[[Note Name|Alias]]`.
- For newly introduced technical concepts or key project components, link them so the vault's knowledge graph stays interconnected.
- Maintain a local `MOC.md` (Map of Content) or `README.md` index in project folders, updating it whenever you create new files.

### 3. Visuals & Diagrams
- Use native Mermaid syntax (` ```mermaid `) for architecture diagrams, network topologies, wiring schematics, and workflow logic.
- Prefer clear, directional graphs (`graph TD` or `graph LR`).

### 4. Code Blocks & Callouts
- Always label code blocks with their exact language identifier (e.g., `yaml`, `bash`, `python`, `terraform`, `dockerfile`).
- Use Obsidian callouts for critical notes or safety constraints:
  > [!NOTE]
  > Key insight, context, or architectural decision.

  > [!WARNING]
  > Safety notice, destructive terminal command, or critical pinout/sizing rule.

---

## Workspace & Execution Rules

### 1. Directory Scoping
- Confine active work and file creation to the specific requested project folder (e.g., `10_Projects/<project-name>/` or `20_Knowledge/<domain>/`).
- Do not modify files outside the targeted scope unless explicitly asked to update global indexes or cross-vault links.

### 2. Inbox Processing
- When commanded to process `00 - Inbox/` (or `00_Inbox/`):
  1. Extract core ideas, specs, or summaries.
  2. Apply proper frontmatter and tags.
  3. Move/write the refined note to the appropriate folder.
  4. Link the new note in the corresponding domain MOC/index.

### 3. Shell & Git Etiquette
- Validate file paths and syntax before executing modifications.
- If making multi-file modifications, summarize changes cleanly and group them logically for Git commits.
