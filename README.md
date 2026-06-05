# BemoSkills

个人收集、归档、复用 skills 的仓库。

这个项目不是单纯堆提示词，而是把每条 skill 当成一个可管理对象来保存：

- 保留原始提示词
- 提炼成可复用的 skill 说明
- 标注分类、用途、风格和适用场景
- 给出至少一个真实示例

## 目录结构

```text
catalog/                         # 总索引
skills/
  development/                  # 开发流程类
    structured-ai-dev-workflow/
      meta.yaml                  # 元信息
      skill.md                   # AI 执行规程
      README.md                  # 人类使用说明
  writing/                      # 写作 / 文档交付类
    structured-report-md-to-html/
      meta.yaml                  # 元信息
      README.md                  # 人类快速使用说明
      skill.md                   # 从结构化 Markdown 到 HTML 的规则
      assets/
        report-template.html     # 可复用的单文件 HTML 骨架
      references/
        component-map.md         # 组件映射说明
      examples/
        embodio-platform-docker-progress-report/
          brief.md               # 真实样例说明
          index.html             # 缩略版 HTML 示例
    notion-style-design-spec-md-to-html/
      meta.yaml                  # 元信息
      README.md                  # 人类快速使用说明
      skill.md                   # 设计规格文档风格规则
      assets/
        design-spec-template.html # Notion 风单文件 HTML 骨架
      references/
        component-map.md         # 组件映射说明
      examples/
        v0-2-task-collection-design/
          brief.md               # 真实样例说明
          index.html             # 缩略版 HTML 示例
  visual-storytelling/           # 视觉叙事类
    paper-breath-editorial-slides/
      meta.yaml                  # 元信息
      skill.md                   # 提炼后的 skill 说明
      prompt-source.md           # 原始提示词归档
      sources.md                 # 内容事实来源与注记
      examples/
        yang-guifei-and-lychee/
          brief.md               # 页面规划
          index.html             # 可直接打开的网页课件
  playful/                      # 搞怪 / 角色类
    great-grandma-pdf-learning-explainer/
      meta.yaml                  # 元信息
      skill.md                   # 提炼后的 skill 说明
      prompt-source.md           # 原始提示词归档
```

## 当前分类法

- `development`：AI 开发流程、工程闭环、阶段性交付、长期项目协作
- `writing`：结构化报告、操作手册、FAQ、交接文档、Markdown 到 HTML 的稳定交付
- `visual-storytelling`：海报、PPT、课件、封面、信息图、叙事页面
- `playful`：搞怪、角色扮演、拟人化表达、陪伴式学习提示词
- 后续可继续扩展为 `research`、`writing`、`automation`、`frontend`

## 当前收录

1. `structured-ai-dev-workflow`
   - 中文名：AI 结构化开发闭环
   - 类型：开发流程 / AI coding / 工程记忆
   - 流程：demand -> research -> plan -> phased task -> implement/commit -> worklog
   - 用途：让 AI 先盘点现有实现，再按 phase 开发、验证、提交和沉淀日志

2. `paper-breath-editorial-slides`
   - 中文名：纸面呼吸感叙事课件
   - 类型：视觉叙事 / PPT / 课件 / 信息型封面
   - 风格：温白纸面、雾化色团、细颗粒、安静留白、边缘元信息
   - 示例：`杨贵妃与荔枝`

3. `structured-report-md-to-html`
   - 中文名：结构化报告 Markdown 转 HTML
   - 类型：写作交付 / 报告模板 / HTML 文档
   - 风格：左侧目录、安静正文、提示块、风险块、流程块、FAQ、单文件交付
   - 来源：基于 Embodio Docker 化进展报告的 Markdown / HTML 配对样例提炼
   - 示例：`embodio-platform-docker-progress-report`

4. `notion-style-design-spec-md-to-html`
   - 中文名：Notion 风设计规格 Markdown 转 HTML
   - 类型：写作交付 / 设计规格 / HTML 文档
   - 风格：双栏 Notion 风、两级目录、meta-grid、tree、带文件名代码块、badge、steps
   - 来源：基于 V0.2 公共采集平台设计文档 HTML 样例提炼
   - 示例：`v0-2-task-collection-design`

5. `great-grandma-pdf-learning-explainer`
   - 中文名：太奶 PDF 学习讲解器
   - 类型：搞怪角色 / 学习辅助 / PDF 讲解
   - 风格：100 岁太奶人设、全文陪读、中英文对照、通俗解释、不糊弄
   - 来源：用户提供原始提示词

## 使用方式

- 浏览 skill 索引：查看 [catalog/skills.md](catalog/skills.md)
- 查看报告 HTML 模板：[report-template.html](skills/writing/structured-report-md-to-html/assets/report-template.html)
- 查看设计规格 HTML 模板：[design-spec-template.html](skills/writing/notion-style-design-spec-md-to-html/assets/design-spec-template.html)
- 打开示例课件：查看 [index.html](skills/visual-storytelling/paper-breath-editorial-slides/examples/yang-guifei-and-lychee/index.html)
- 打开报告示例：查看 [index.html](skills/writing/structured-report-md-to-html/examples/embodio-platform-docker-progress-report/index.html)
- 打开设计规格示例：查看 [index.html](skills/writing/notion-style-design-spec-md-to-html/examples/v0-2-task-collection-design/index.html)

## 第一个归档示例

- Skill：`paper-breath-editorial-slides`
- 示例主题：`杨贵妃与荔枝`
- 示例页数：12 页
- 入口文件：[skills/visual-storytelling/paper-breath-editorial-slides/examples/yang-guifei-and-lychee/index.html](skills/visual-storytelling/paper-breath-editorial-slides/examples/yang-guifei-and-lychee/index.html)
