---
name: obsidian-toread
description: Use when the user wants to add an article, book, or resource to their Obsidian to-read list. Triggers on requests like "add to my reading list", "save this for later", "add to to-read", or when the user shares a URL to bookmark for later reading.
---

# Obsidian To-Read

## Overview

Add items to the Obsidian `To-Read.md` file. Always attempt to fetch the URL to extract title/author; handle fetch failures gracefully.

## File

```
~/Documents/obsidian-repo/To-Read.md
```

## Table Schema

| # | 标题 | 类型 | 来源/作者 | 优先级 | 添加日期 | 备注 |

## Workflow

1. Read the current `To-Read.md` via obsidian MCP `read_note` to get the existing table content
2. Fetch the URL to extract title, author, and summary (see Fetching URL Metadata below)
3. Determine the next `#` number from the last row's first column
4. Insert the new row into the "待阅读" section _before_ the "已读完" section marker
5. Write the updated file using Bash heredoc (NOT MCP write_note — it doesn't persist to disk):

```bash
cat > ~/Documents/obsidian-repo/To-Read.md << 'ENDOFFILE'
...full file content with new row inserted...
ENDOFFILE
```

## Defaults

| Field    | Default                                                                              |
| -------- | ------------------------------------------------------------------------------------ |
| 类型     | `文章` (web), `书籍` (book), `视频` (video), `论文` (paper) — infer from URL/context |
| 优先级   | `待定` unless user specifies otherwise                                               |
| 添加日期 | Today's date in YYYY-MM-DD                                                           |

## Fetching URL Metadata

1. Try `WebFetch` first with the URL
2. If WebFetch returns 403 (bot-blocked), fall back to `curl` with a browser User-Agent:

```bash
curl -sL -H "User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36" "<URL>"
```

3. Extract title from `<title>` tag, description from `<meta name="description" content="...">`
4. Only if both methods fail: use URL domain as title, note "待补充标题" in 备注

## Edge Cases

- **Duplicate URL**: grep the current table for the URL; warn user if already present, don't add duplicate
- **User provides title/notes**: always prefer user-supplied values over auto-extracted ones
- **First item in empty section**: insert row directly after the table header
