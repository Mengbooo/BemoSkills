---
name: bemoskill-generator
description: Use when the user wants to create a new skill for their BemoSkills collection, or when asked to "generate a bemoskill" or "add a skill to BemoSkills". Generates meta.yaml, skill.md, and updates the catalog in the correct BemoSkills format.
---

# BemoSkill Generator

## Overview

Generate a new skill in the [BemoSkills](https://github.com/Mengbooo/BemoSkills) repository format. Each skill lives under `skills/{category}/{skill-id}/` with a `meta.yaml` for catalog metadata and `skill.md` for the AI-executable instructions.

## BemoSkills Repository Structure

```
BemoSkills/
├── catalog/
│   ├── skills.json        # Machine-readable index
│   └── skills.md          # Human-readable catalog
├── skills/
│   └── {category}/
│       └── {skill-id}/
│           ├── meta.yaml  # Metadata for catalog
│           └── skill.md   # AI-executable instructions (Claude Code SKILL.md)
├── index.html             # Showcase site
└── README.md
```

## Existing Categories

Choose the most appropriate category for the new skill:

| Category              | Use for                                        |
| --------------------- | ---------------------------------------------- |
| `development`         | Dev workflows, AI coding, CI/CD                |
| `writing`             | Document generation, markdown-to-HTML, reports |
| `visual-storytelling` | Visual design, slides, diagrams                |
| `playful`             | Fun/creative tools, personas, explainers       |
| `productivity`        | Tool integration, automation workflows         |

Create a new category only if the skill genuinely doesn't fit any existing one.

## meta.yaml Format

```yaml
id: kebab-case-id
title: English Title
title_zh: 中文标题
status: active # active or archived
category:
  - primary-category
  - secondary-tag
formats:
  - format-1
language:
  - zh-CN
  - en
best_for:
  - 场景一
  - 场景二
source: distilled from real workflow with Claude Code
collected_on: YYYY-MM-DD
```

### Field Guidelines

- `id`: kebab-case, matches the directory name. Unique across the entire catalog.
- `title`: concise English title, max 8 words
- `title_zh`: natural Chinese title with clear action/domain
- `status`: `active` for current use, `archived` for reference-only
- `category`: first entry is the primary category folder name
- `best_for`: 2-4 concrete use cases in Chinese
- `source`: brief origin note (e.g. "distilled from X workflow")

## skill.md Format

Standard Claude Code SKILL.md with YAML frontmatter:

```markdown
---
name: skill-id
description: Use when [specific triggering conditions]. [What it does in one sentence.]
---

# Skill Title

## Overview

One-paragraph summary of what this skill does and when to use it.

## Core Workflow / Pattern

Step-by-step or pattern description.

## Common Mistakes

Table of mistakes and fixes.

## Quality Checklist (if applicable)

- [ ] Checklist item
```

### Frontmatter Guidelines

- `name`: must match the directory name and meta.yaml `id`
- `description`: starts with "Use when...", describes triggering conditions (not workflow summary). See CSO principle below.

**CSO Principle**: Description = triggering conditions only, NOT workflow summary. If the description summarizes what the skill does step-by-step, Claude may follow the description instead of reading the full skill body.

Good: `Use when setting up Claude Code to manage an Obsidian vault via MCP, or configuring free Obsidian sync to GitHub`
Bad: `Use when setting up Obsidian — first add MCP, then configure git sync, then install plugin`

## Catalog Update

After creating the skill files, update both catalog files:

### catalog/skills.json

Add an entry to the JSON array:

```json
{
  "id": "skill-id",
  "title": "English Title",
  "title_zh": "中文标题",
  "status": "active",
  "category": ["primary", "tag"],
  "keywords": ["kw1", "kw2", "kw3"],
  "path": "skills/category/skill-id",
  "examples": []
}
```

### catalog/skills.md

Add under the appropriate category section:

```markdown
### `skill-id`

- 中文名：中文标题
- 状态：active
- 适用：场景一、场景二
- 关键词：kw1、kw2、kw3
- 目录：[skills/category/skill-id](skills/category/skill-id)
```

## Workflow

1. **Understand** the skill purpose from user's description
2. **Choose** the best-fitting category (or propose a new one)
3. **Generate** `meta.yaml` with proper metadata
4. **Generate** `skill.md` with frontmatter + body
5. **Write** files to `skills/{category}/{skill-id}/`
6. **Update** both `catalog/skills.json` and `catalog/skills.md`
7. **Commit** and push to the BemoSkills repository

## Important Notes

- The repo path is `/Users/qiumengbo.123/Desktop/BemoSkills`
- Always update BOTH catalog files when adding a skill
- The skill.md `name` in frontmatter MUST match the directory name
- Use `active` status for new skills by default
- Keywords should include both English and Chinese terms
