---
name: obsidian-write
description: Use when the user wants to research a topic and save the results as a note in their Obsidian vault, or when asked to "research and write to obsidian". Handles web search, source gathering, report synthesis, writing to vault, and git commit/push.
---

# Obsidian Research Pipeline

## Overview

Research a topic via web search, synthesize findings into a structured markdown report, write to the Obsidian vault, and commit/push to GitHub.

## Workflow

### Step 1 — Search

Run 3-5 parallel WebSearch queries covering different angles of the topic. Use varied keywords and both English and Chinese terms when the topic is bilingual.

### Step 2 — Synthesize

Organize findings into a structured report:

```markdown
---
tags: [relevant, tags]
created: YYYY-MM-DD
---

# Title

## Section 1 — Problem breakdown

## Section 2 — Core findings (with inline links to sources)

## Section 3 — Implications / action items

## References (full URLs for every cited source)
```

**Critical:** Every referenced article, paper, or source MUST have a clickable markdown link. Use inline links `[text](url)` in the body and full citation links in the References section.

### Step 3 — Write to Vault

Write the report to `~/Documents/obsidian-repo/<filename>.md`.

**CRITICAL:** The Write tool requires reading a file before overwriting it. If creating a new file, use Bash with heredoc:

```bash
cat > ~/Documents/obsidian-repo/filename.md << 'ENDOFFILE'
...content...
ENDOFFILE
```

### Step 4 — Commit and Push

```bash
cd ~/Documents/obsidian-repo && git add -A && git commit -m "message" && git push
```

## Quality Checklist

- [ ] At least 3 distinct web searches conducted
- [ ] Every factual claim has a source link
- [ ] References section has full URLs (not just paper titles)
- [ ] Report is well-structured with clear sections
- [ ] Frontmatter includes tags and created date
- [ ] Changes committed and pushed to GitHub

## Common Mistakes

| Mistake                                                 | Fix                                     |
| ------------------------------------------------------- | --------------------------------------- |
| References without URLs                                 | Every source must have a clickable link |
| Single search query                                     | Run 3-5 queries with different angles   |
| Writing to vault without committing                     | Always commit + push after writing      |
| Using Write tool on new files (fails if not Read first) | Use Bash heredoc for new files          |
