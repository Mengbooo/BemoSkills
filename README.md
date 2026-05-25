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
```

## 当前分类法

- `development`：AI 开发流程、工程闭环、阶段性交付、长期项目协作
- `visual-storytelling`：海报、PPT、课件、封面、信息图、叙事页面
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

## 使用方式

- 浏览 skill 索引：查看 [catalog/skills.md](/Users/qiumengbo.123/Desktop/BemoSkills/catalog/skills.md)
- 打开示例课件：查看 [index.html](/Users/qiumengbo.123/Desktop/BemoSkills/skills/visual-storytelling/paper-breath-editorial-slides/examples/yang-guifei-and-lychee/index.html)

## 第一个归档示例

- Skill：`paper-breath-editorial-slides`
- 示例主题：`杨贵妃与荔枝`
- 示例页数：12 页
- 入口文件：[skills/visual-storytelling/paper-breath-editorial-slides/examples/yang-guifei-and-lychee/index.html](/Users/qiumengbo.123/Desktop/BemoSkills/skills/visual-storytelling/paper-breath-editorial-slides/examples/yang-guifei-and-lychee/index.html)
