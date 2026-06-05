# notion-style-design-spec-md-to-html

把结构化 Markdown 设计文档转成同类的 Notion 风单文件 HTML。

## 这个 skill 解决什么问题

当你已经有一份 PRD 拆解、技术设计或前后端对接说明，希望交付成：

- 更像正式设计规格文档
- 左侧两级目录清楚
- 顶部有 meta 信息区
- 代码块带语言和文件名
- 有 badge、步骤列表、卡片组、树形范围图

就适合用这个 skill。

## 最快用法

直接这样说：

```text
按 notion-style-design-spec-md-to-html 处理这个 Markdown：
1. 先读懂结构和章节层级
2. 保留原始设计要点、代码片段、文件改动表和 API 契约
3. 转成同风格单文件 HTML
4. 要有两级目录、header meta-grid、tree、带文件名代码块、badge、steps 和移动端适配
```

## 仓库内入口

- 规则说明：
  [skill.md](skills/writing/notion-style-design-spec-md-to-html/skill.md)
- 组件映射：
  [component-map.md](skills/writing/notion-style-design-spec-md-to-html/references/component-map.md)
- HTML 骨架：
  [design-spec-template.html](skills/writing/notion-style-design-spec-md-to-html/assets/design-spec-template.html)
- 真实示例：
  [index.html](skills/writing/notion-style-design-spec-md-to-html/examples/v0-2-task-collection-design/index.html)

## 推荐场景

- 产品设计说明
- 前后端联调文档
- 技术方案规格说明
- API 契约文档
- 分模块实施计划

## 不推荐场景

- 周报 / 进展报告
- 运维交接手册
- 海报或网页 PPT
- 营销页面
