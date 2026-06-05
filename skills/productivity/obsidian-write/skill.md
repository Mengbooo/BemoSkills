---
name: obsidian-write
description: Use when the user wants to research a topic and save the results into their Obsidian vault, or when asked to "write to obsidian". Handles web search, source gathering, report synthesis, vault routing, content unit structuring, To-Read entry creation, and git commit/push.
---

# Obsidian Write

## Overview

Research a topic via web search, synthesize findings into a structured markdown report, route to the correct vault directory, annotate with content unit metadata (dbs-content-system), create a To-Read tracking entry, and commit/push to GitHub.

## Vault Structure

```
vault/                                  # ~/Documents/obsidian-repo
├── Home.md / CLAUDE.md / To-Read.md    # 仪表盘 (root only)
├── 00-结构化索引/                       # 关系索引 + 来源注册 + 去重索引
├── inbox/                              # 快速捕获，待整理
├── areas/
│   ├── agent/      🤖 Agent            # Agent/Skill/示教学习
│   ├── ai/         🤖 AI               # AI/LLM 理论/分析
│   └── engineering/ 🛠 工程             # 工具配置/工程实践
├── 05-主题地图/                         # 按主题聚合内容单元
├── resources/                          # 工具/网站/资源收集
├── readings/                           # 阅读笔记 + To-Read 追踪
├── projects/ / templates/ / archives/  # 项目/模板/归档
```

## Content Routing

1. **阅读/文章评论?** → `readings/` + To-Read 元数据
2. **Agent/Skill 相关?** → `areas/agent/`
3. **AI/LLM 理论/分析?** → `areas/ai/`
4. **工具配置/工程?** → `areas/engineering/`
5. **工具/网站/资源收集?** → `resources/`
6. **项目文档?** → `projects/`
7. **不确定?** → `inbox/`

## Workflow

### Step 1 — Search

Run 3-5 parallel WebSearch queries covering different angles.

### Step 2 — Synthesize

Structured report with proper frontmatter. Every source MUST have a clickable link.

### Step 3 — Route to Directory

Use the routing table above.

### Step 4 — Write

Write the file to `~/Documents/obsidian-repo/{target-dir}/{filename}.md`.

### Step 5 — Content Unit Annotation (dbs-content-system)

**CRITICAL: After writing, annotate the article with content unit metadata.**

Every research report must include a `content_unit` block in its frontmatter:

```yaml
# Content Unit (dbs-content-system)
content_unit:
  id: {QST|CON|OPI|CAS|SOL}-{序号}
  type: QST | CON | OPI | CAS | SOL
  title: "简短标题"
  canonical: areas/{领域}/{文件名}.md
  version: "1.0"
  source_documents:
    - web-research
    - notion-migration
  themes:
    - 主题A
    - 主题B
  keywords:
    - 关键词1
    - 关键词2
  relationships:
    - target: {其他单元ID}
      type: 回应 | 解释 | 证明 | 冲突
```

**Content unit type selection:**

| 类型 | 全称 | 何时使用 |
|------|------|---------|
| `QST` | Question | 文章提出并回答了一个核心问题 |
| `CON` | Concept | 文章定义/解释了一个概念或框架 |
| `OPI` | Opinion | 文章表达了分析性观点或判断 |
| `CAS` | Case | 文章记录了具体事件、数据或案例 |
| `SOL` | Solution | 文章给出了可操作的方案或路径 |

If an article covers multiple types, pick the dominant one for `type` and add cross-references in `relationships`.

**ID assignment:** Check `00-结构化索引/关系索引.md` for the next available ID in each category.

### Step 6 — Create To-Read Entry

Create a companion reading note in `readings/` using `templates/tpl-reading-item.md` format:

- `status: done` — research reports are completed on creation
- Include `[[wiki-link]]` back to the main report
- Include 3-5 key takeaways
- List external reference links

### Step 7 — Commit and Push

```bash
cd ~/Documents/obsidian-repo && git add -A && git commit -m "描述变更" && git push
```

## Quality Checklist

- [ ] At least 3 distinct web searches conducted
- [ ] Every factual claim has a source link
- [ ] References section has full URLs
- [ ] Frontmatter includes tags and created date
- [ ] File routed to correct vault directory
- [ ] **Content unit metadata added (id/type/themes/keywords/relationships)**
- [ ] **Relationship index updated if new cross-references exist**
- [ ] Companion reading note created in `readings/`
- [ ] Changes committed and pushed to GitHub

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Floating files at vault root | Route to `areas/`, `readings/`, or `inbox/` |
| Missing content unit annotation | Every research report needs `content_unit` frontmatter |
| Wrong content unit type | QST=问题, CON=概念, OPI=观点, CAS=案例, SOL=方案 |
| No cross-references in relationships | Link to related units via their IDs |
| Forgetting To-Read entry | Every research report needs a companion reading note |
| Not committing after write | Always commit + push |
