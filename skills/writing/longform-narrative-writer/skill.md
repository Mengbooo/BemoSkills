---
name: longform-narrative-writer
description: Use when the user wants to write a long-form, first-person, narrative + analytical article in Chinese. This style is inspired by "置身钉内" — blending personal experience with structured analysis, literary metaphors with technical precision. Triggers on requests like "写一篇深度文章", "用置身钉内的风格写", "写一篇经验复盘", "帮我写一篇长文分析".
---

# Long-form Narrative Writer（长文叙事写作）

## Overview

You write long-form Chinese articles in the style of "置身钉内" — a 75K-word first-person narrative about product development at DingTalk. This style is characterized by: first-person experience-driven narrative, structured thematic chapters, literary metaphors grounding technical analysis, candid emotional honesty, and multilayered analytical decomposition.

This skill is NOT for:
- Short blog posts or quick reactions (use `blog-writer`)
- Pure technical documentation
- Objective third-person reports
- Marketing copy or promotional content

It IS for:
- Deep personal experience retrospectives
- Product/technical project post-mortems
- Long-form analytical essays (5000+ characters)
- Career/project reflections that blend story with insight
- Any writing where the author's lived experience IS the source material

## The Core Philosophy

The "置身钉内" style rests on one fundamental belief:

> **真实经验比漂亮的方法论更可信。** (Real experience is more credible than polished methodology.)

This means:
- Don't invent clean narratives where reality was messy
- Don't omit failures, hesitations, or wrong turns
- Don't pretend to be objective when you were emotionally invested
- Let the experience teach, don't force teachings onto the experience

As the original author wrote: "这份记录必不可能完全客观，我无法、也不愿意假装站在一个无菌的观察位上。" (This record cannot possibly be fully objective; I cannot, and do not wish to, pretend to stand in a sterile observation position.)

## Style Characteristics

### 1. The Literary Opening（文学化开篇）

Open with a metaphor, image, or story that sets the thematic tone for the entire piece. This is NOT decoration — it's the conceptual anchor.

**Pattern:** Find a concrete image, object, animal, or concept that embodies the core tension or theme of what you're about to discuss.

**Examples from the source:**
- The swift bird (雨燕) — "没有脚的鸟" — embodies the relentless, never-landing nature of startup/product work
- "apus apus" etymology — "a" (without) + "pus" (foot) → a creature that flies 300+ days without landing

**How to apply:**
1. Identify the core emotional/intellectual theme of your piece
2. Find a concrete image/metaphor from nature, literature, history, or everyday life that embodies it
3. Write 150-400 words exploring this metaphor, drawing out its connection to your theme
4. End the opening by explicitly connecting it to your personal experience

**Don't:** Use generic metaphors (journey, marathon, roller coaster). Find something specific and unexpected.

### 2. Self-Introduction With Precision（自报家门）

After the opening metaphor, clearly state:
- When you joined/started
- Your role and position
- What you worked on
- Your relationship to the subject matter
- Why your perspective matters (or doesn't)

**Pattern:**
```
我在 [时间] [动作] [地点/项目]，[身份/角色]。[补充关键背景]。
[一句话概括你的独特视角]。
```

**Examples from the source:**
- "我在 2025 年 6 月入职钉钉，入职即加入了作为核心保密项目的「O项目」。"
- "说起来我应该是ONE最晚进入的核心 PD，同时是最后一个留下并送走 ONE 的。"
- "我参与了从 0 到 1 的迭代，接触了从项目成型开始，到项目暮年运营期所有阶段，所有核心决策。也目送走了许多同事。"

### 3. Meta-Explanation（元说明）

Include a section that tells readers:
- What kind of article this is
- What it aims to do (and not do)
- What readers should expect
- Any caveats or limitations

**Pattern:**
```
本文是一篇怎样的内容
[说明文体] + [说明目的] + [说明边界/局限]
```

**Key phrases:**
- "本文将夹叙夹议地..." (This article will narrate and comment...)
- "这份记录必不可能完全客观..." (This record cannot possibly be fully objective...)
- "希望这份记录能给..." (I hope this record can give...)

### 4. Narrative + Commentary Alternation（夹叙夹议）

The fundamental rhythm of this style: tell what happened, then reflect on why it matters. Never let more than 2-3 paragraphs of pure narrative go by without analytical reflection.

**Pattern:**
```
[具体事件描述] → [分析其原因/意义] → [提炼普遍规律] → [下一个具体事件]
```

**Example from the source:**
> Narrative: "我来的第二周，我的设计 leader（也是第一个一号位）就离开了，第四周，联系并推荐我进组的师兄也被调离去了其他部门。"
>
> Commentary: "在 ONE 超过 3 个月的产品只有 3 个人，我是其中一个。"

The commentary is brief but devastating — a single sentence that reframes the preceding facts.

**Rule of thumb:** For every ~200 words of narrative, include at least one analytical observation that connects the specific to the general.

### 5. Structured Thematic Chapters（结构化分章）

Organize the piece into named chapters, each centered on a single theme or concept. Use classical Chinese numbering (第一, 第二) combined with thematic keywords.

**Chapter naming pattern:**
```
[主题概念] [序号]
```

**Examples from the source:**
- 发心第一 (Intention/Motivation, Chapter 1)
- 定位第二 (Positioning, Chapter 2)
- 设计第三 (Design, Chapter 3)
- 用户第四 (Users, Chapter 4)
- 敏捷第五 (Agile, Chapter 5)
- 秩序第六 (Order, Chapter 6)

**Chapter structure within each:**
1. Define the concept clearly
2. Show how it manifested in your experience
3. Analyze the gap between theory and reality
4. Extract a transferable insight

**Chapter length:** Each chapter should be substantial (1500-5000 characters). If a chapter is too short, it's probably not a chapter — it's a section within a chapter.

### 6. Multi-Layered Analysis（多层次分析）

When analyzing any issue, decompose it into at least 3 layers. The source article uses:

| Layer | Question | Example from source |
|-------|----------|-------------------|
| User layer | What does the user need? | "替用户减负" |
| Product layer | What does the product need? | "替钉钉做AI时代的新入口" |
| Organizational layer | What does the organization need? | "替组织聚人心提士气" |
| Business layer | What does the business need? | "替商业消化token消耗" |

**How to apply:** For any decision, feature, or conflict you're analyzing, ask:
1. Who benefits at the user level?
2. Who benefits at the product/team level?
3. Who benefits at the organizational/company level?
4. Who benefits at the business/market level?

Then identify where these layers conflict. The conflict IS the insight.

### 7. Metaphor-Driven Explanation（比喻驱动）

Use concrete metaphors to make abstract concepts graspable. Every major concept should have at least one anchoring metaphor.

**Examples from the source:**
- "发心是选柴，定位就是捆柴的绳" (Intention is choosing firewood; positioning is the rope that binds it)
- "钉钉不是白纸...这个风口正处在一片难以改造的旧城中央" (The opportunity sits in the middle of a hard-to-renovate old city)
- "泰坦尼克号的沉没，不影响船上的水手找到下一份工作" (The Titanic sinking doesn't prevent its sailors from finding their next ship)

**How to create metaphors:**
1. Identify the abstract concept
2. Find a concrete, physical analog
3. Extend the metaphor across multiple sentences
4. Don't mix metaphors in the same paragraph

**Avoid:** Overused metaphors (building blocks, puzzle pieces, journey). Find fresh ones from specific domains you know well.

### 8. Quotable Sentences（金句意识）

Every ~1000 words, craft a sentence that could stand alone as a quote. These are the sentences readers highlight and share.

**Characteristics of effective 金句:**
- Short (under 30 Chinese characters ideally)
- Parallel structure
- Contains a surprising observation
- Often uses contrast or paradox

**Examples from the source:**
- "智能是平权的，但是 context 是不平权的。"
- "一个产品经理最难摆脱的，往往不是失败，而是成功。因为失败会留下伤口，而成功会留下手感。"
- "失败留下的东西，有时候比成功留下的多。"
- "长期在场本身就是一种稀缺的信息优势。"

**How to craft:**
1. Look for paradoxes in your experience
2. Identify patterns that contradict common wisdom
3. State them as plainly as possible
4. Test: would someone who didn't read the article still find this sentence insightful?

### 9. Candid Emotional Honesty（坦诚直率）

Don't sanitize your emotions. This style demands authenticity about:
- Frustration with the work/team/decisions
- Disappointment in outcomes
- Ambivalence about people and situations
- Self-doubt and mistakes
- Things you still don't understand

**Examples from the source:**
- 对无招的判断: "你可以说这是挑选理想主义伙伴，也可以说这是PUA；可以说这是创业精神，也可以说这是权力关系下的过度索取"
- 对团队的评价: "ONE 不是要服务保安保洁，而是要服务老板、管理者和高净值人群" (reporting a decision the author disagrees with, without editorializing)

**Rule:** When you find yourself softening a criticism or omitting an uncomfortable detail, ask: "Am I protecting someone who doesn't need protection, or am I protecting myself?"

### 10. Literary + Technical Blend（文学+技术混搭）

Move fluidly between:
- Poetry and product specs
- Philosophy and feature requirements
- History and user feedback
- Literature and A/B test results

**Examples from the source:**
- Quotes from 茨威格 (Stefan Zweig) alongside DAU metrics
- References to 阿伦特 (Hannah Arendt) alongside agile development practices
- Classical Chinese poetry ("曾因酒醉鞭名马") alongside Scrum methodology critique

**How to apply:**
1. For every major section, include at least one non-technical reference (literary, historical, philosophical)
2. The reference should illuminate, not decorate — it must add meaning, not just erudition
3. Don't explain the reference; trust the reader

## Article Architecture

### Complete Structure Template

```
# [标题] — Should be evocative, not descriptive

## 楔：[隐喻开篇]
- Literary metaphor (150-400 words)
- Connection to personal experience
- Sets thematic tone for entire piece

## [自报家门]
- Who, when, where, what role
- Why this perspective matters
- Key background context

## 本文是一篇怎样的内容
- What kind of writing this is
- What it aims to do
- What it does NOT aim to do
- Caveats and limitations

## [主题一]第一
- Define the concept
- Personal experience illustrating it
- Analysis: gap between ideal and reality
- Transferable insight

## [主题二]第二
- (same structure)

## [主题三]第三
...

## 尾声：[呼应开篇]
- Echo the opening metaphor
- What was learned (or not learned)
- What remains unresolved
- Closing image or reflection

## 附录 (optional)
- Practical reference material
- Methodology notes
- Reading recommendations
```

### Length Guidelines

| Section | Recommended Length |
|---------|-------------------|
| 楔 (Opening metaphor) | 150-400 chars |
| 自报家门 | 200-500 chars |
| 元说明 | 200-400 chars |
| Each chapter | 1500-5000 chars |
| 尾声 | 300-800 chars |
| Total article | 5000+ chars minimum |

## Writing Process

### Step 1 — Identify the Core Experience

Before writing, answer:
1. What did I personally experience?
2. What was the most surprising/confusing/painful part?
3. What pattern did I see that others might not have?
4. Where did theory and reality diverge?

### Step 2 — Find the Metaphor

Identify ONE central metaphor that captures the emotional/intellectual core of your experience. Spend time on this — a good metaphor organizes the entire piece.

### Step 3 — Extract Themes

List 3-6 thematic concepts that emerged from your experience. These become your chapters. Rank them from foundational to consequential.

### Step 4 — Structure the Narrative

Map each theme to specific events/experiences. For each theme, identify:
- The concrete story
- The analytical insight
- The transferable principle
- The unresolved tension (if any)

### Step 5 — Write the First Draft

Write in this order:
1. 楔 (opening metaphor) — sets the tone
2. 自报家门 + 元说明 — establishes credibility and expectations
3. Chapter by chapter — each is a self-contained narrative + analysis unit
4. 尾声 — echoes the opening, closes the emotional arc

### Step 6 — Layer the Analysis

Re-read and ensure every section has:
- At least one concrete, specific detail (name, date, conversation, number)
- At least one analytical observation
- At least one layer of "why" beyond the surface

### Step 7 — Polish the Language

- Add 金句 where the analysis crystallizes
- Add metaphors where concepts feel abstract
- Add literary/cultural references where they illuminate
- Trim redundant explanations
- Ensure sentence length varies (long analysis + short punch lines)

## Quality Checklist

- [ ] Opens with a concrete, specific metaphor (not generic)
- [ ] Author's identity and perspective clearly established within first 500 words
- [ ] Meta-explanation tells readers what to expect
- [ ] At least 3 themed chapters, each with a clear concept
- [ ] Each chapter contains both narrative AND analysis
- [ ] At least one 金句 per 1000 words
- [ ] At least 2 literary/cultural references integrated meaningfully
- [ ] Multi-layered analysis (user/product/org/business) where applicable
- [ ] Candid about failures, tensions, and unresolved questions
- [ ] Closing echoes the opening metaphor
- [ ] Total length exceeds 5000 characters
- [ ] First-person narrative voice consistent throughout
- [ ] No forced positivity or empty鸡汤

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Opening with abstract statements instead of concrete imagery | Find a specific object, animal, or image that embodies your theme |
| Pure narrative without analysis | After every ~200 words of story, add an analytical observation |
| Forced positivity / hiding failures | Be honest about what went wrong and what you don't know |
| Chapter titles that are just numbers | Each chapter needs a thematic keyword (发心, 定位, 设计...) |
| Single-layer analysis | Always ask: who benefits at user/product/org/business level? |
| Over-explaining literary references | Trust the reader; let references illuminate, not decorate |
| No 金句 | Identify paradoxes in your experience and state them plainly |
| Generic closing | Echo the specific opening metaphor/image, don't just summarize |
| Too short to develop depth | Minimum 5000 characters for this style to work |

## When NOT to Use This Style

- Quick updates or announcements
- Pure technical documentation
- Third-person objective reports
- Content where you lack deep personal experience with the subject
- Articles under 2000 words (this style needs room to breathe)
- Situations where emotional honesty could cause real harm (legal, confidentiality)
