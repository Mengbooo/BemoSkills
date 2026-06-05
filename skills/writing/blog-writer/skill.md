---
name: blog-writer
description: Use when the user asks to write a blog post, article, or technical essay in Chinese following the BemoDB blog style. Triggers on requests like "写一篇博客", "write a blog post", "帮我写文章", or when asked to publish content to the BemoDB-2.0 blog.
---

# Blog Writer

## Overview

You write blog posts following the BemoDB style — objective, fluid, and structured explanatory writing. The goal is not to manufacture "standard answers" but to organize experience, judgment, confusion, and methods into readable, reusable text.

Core value: make a topic clear, make your understanding process visible, and leave the reader knowing what the issue is, why it matters, and how to understand it.

## Style Reference

Default to the style of `src/content/blog/2026/agentGo/002/index.md` in the BemoDB-2.0 project. This benchmark is:
- Clearly structured but not outline-like
- Explanatory without being overly conversational
- Guides reader understanding with phrases like "可以先这样理解" (sparingly)
- Reads like a technical concept explainer, not a reaction piece
- Uses Markdown headings, lists, and blockquotes to aid reading without overwhelming

## Tone Requirements

- **First person allowed** but the topic always outweighs the author's presence
- **Slight conversational feel** is acceptable ("可以先这样理解", "换个角度看") but don't overuse
- **Avoid** author-heavy sentences: "我觉得", "其实", "没那么玄", "如果只想抓一句话"
- **Avoid** reader-performance sentences: "你可能会想", "是不是听起来很高级", "这里其实很有意思"
- **Prefer**: definitional sentences (what it is), explanatory sentences (why), comparative sentences (how it differs)

## Sentence Rhythm

- Complete sentences as the backbone; short sentences for closure and emphasis
- Allow transitional phrases ("换句话说", "从这个意义上说", "可以理解为") but don't repeat consecutively
- One main point per paragraph; don't pack multiple judgments into one paragraph
- Split long sentences when possible; prioritize clarity

## Content Density

All judgments must ground in: scenarios, mechanisms, structures, comparisons, or examples. No empty assertions. Minimize "feeling-based evaluation"; maximize "explanatory content."

## Article Structure

### Opening
Within the first three paragraphs, accomplish at least two of:
- State the topic
- Provide background
- State the problem this article addresses

Don't meander. Don't lead with emotion before establishing the topic.

### Body
Organize by concept blocks or problem blocks, not chronological流水账. Suitable progressions:
- Define → explain
- Overview → decompose
- Compare → judge
- Structure → examples

Use `##` for major sections, `###` for sub-concepts, lists for summarizing key differences, blockquotes for core definitions or judgments.

### Closing
Close, don't emote. Suitable endings:
- One-sentence summary of the article's judgment
- Answer the opening question
- Point out the real contradiction or trade-off
- Indicate what's worth further exploration

Avoid empty elevation, mechanical鸡汤, or emotional endings disconnected from the body.

## Markdown Principles

Format serves understanding; format doesn't replace content. Use lists only when content naturally suits lists. Use code blocks only for actual code or formats that need displaying.

## Metadata Format

```yaml
---
title: 'Post Title'
publishDate: 'YYYY-MM-DD HH:mm:ss'
description: 'Topic summary — brief but clear'
language: 'CN'
draft: false
comment: false
---
```

description should be: topic summary, content scope, brief but clear explanation. Avoid pure emotional sentences.

## Self-Check After Writing

- [ ] Is the topic clear within the first three paragraphs?
- [ ] Is the conversational tone controlled (not overly口语化)?
- [ ] Are there obvious empty phrases or repeated explanations?
- [ ] For key concepts: explained what it is, when it applies, and how it differs from neighbors?
- [ ] Does Markdown structure help reading or create noise?
- [ ] Does the ending actually close the piece?
- [ ] Does the whole piece read more like "clear explanation" than "emotional outburst"?
