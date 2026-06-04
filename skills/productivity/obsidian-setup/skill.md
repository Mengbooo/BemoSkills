---
name: obsidian-setup
description: Use when setting up Claude Code to manage an Obsidian vault via MCP, or configuring free Obsidian sync to GitHub via obsidian-git plugin
---

# Obsidian Setup

## Overview

Connect Claude Code to your Obsidian vault via MCP, and configure free two-way sync to GitHub using the obsidian-git plugin.

## Step 1 — MCP for Claude Code

Register an MCP server so Claude Code can read/write/search your vault.

```bash
claude mcp add -s user obsidian -- npx -y @azerobest/mcpvault --vault ~/path/to/vault
```

Verify:

```bash
claude mcp get obsidian
# Expected: Status: ✓ Connected
```

Grant directory access by adding to `.claude/settings.json`:

```json
{
  "permissions": {
    "additionalDirectories": ["~/path/to/vault"]
  }
}
```

Available tools: file CRUD, search, tag management, frontmatter parsing.

## Step 2 — Obsidian Git for Free Sync

### 2a — Initialize and Push

```bash
cd ~/path/to/vault
git init
git add -A
git commit -m "初始化 Obsidian Vault"
git remote add origin https://github.com/<user>/<repo>.git
git branch -M main
git push -u origin main
```

### 2b — Install Plugin

1. Download `main.js`, `manifest.json`, `styles.css` from [obsidian-git releases](https://github.com/denolehov/obsidian-git/releases/latest)
2. Place in `.obsidian/plugins/obsidian-git/`
3. Open Obsidian → Settings → Community plugins → Enable **Obsidian Git**

### 2c — Configure Auto Sync

In Obsidian Git plugin settings:

| Setting                         | Value     |
| ------------------------------- | --------- |
| Vault backup interval (minutes) | 10        |
| Commit message                  | auto sync |
| Pull changes on startup         | ON        |
| Push changes on startup         | ON        |

## Step 3 — Push Plugin Config to GitHub

```bash
cd ~/path/to/vault
git add -A
git commit -m "启用 obsidian-git 插件并配置自动同步"
git push
```

## Common Issues

- **国内镜像插件市场没有 obsidian-git** → 从 GitHub Releases 手动下载三个文件放到插件目录
- **MCP 连接失败** → 确认 vault 路径正确，`claude mcp get obsidian` 检查状态
- **Git push 权限** → 使用 token 或个人仓库 HTTPS 地址
- **iOS 同步** → 需要 Working Copy App（免费版支持一个私有仓库）
