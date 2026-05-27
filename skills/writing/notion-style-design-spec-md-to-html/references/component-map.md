# Component Map

这个 skill 的关键不是“Markdown 标签对标签”，而是把设计文档里的结构语义，翻译成规范文档组件。

## Header 与文档身份

适用：

- 版本号
- 文档类型
- PRD 路径
- 涉及端
- 日期
- 实施顺序

```html
<header class="header" id="overview">
  <div class="header-eyebrow">Design Specification · V0.2</div>
  <h1>公共采集平台 — H5 与边缘端对接</h1>
  <dl class="meta-grid">
    <dt>PRD</dt><dd>docs/prd/xxx.md</dd>
    <dt>涉及端</dt><dd>Admin · Mobile</dd>
  </dl>
</header>
```

## 两级目录

这个风格推荐显式保留二级目录。

```html
<aside class="toc">
  <div class="toc-title">目录</div>
  <ul class="toc-list">
    <li><a href="#admin">2. Admin 运管端</a></li>
    <li class="toc-l2"><a href="#admin-api">2.5 新增 API</a></li>
  </ul>
</aside>
```

## Tree

适用：

- 改动范围
- 模块边界
- 影响面
- 方案树

```html
<div class="tree"><span class="root">V0.2</span>
<span class="branch">├──</span> <span class="leaf">Mobile</span>
<span class="branch">└──</span> <span class="comment">API 契约</span></div>
```

如果只是普通命令流程，不要用 tree，继续使用代码块或列表。

## 带头部的代码块

这是这个风格的核心组件之一。

```html
<div class="code-block">
  <div class="code-block-header">
    <span class="code-lang">TypeScript</span>
    <span class="code-filename">services/task.ts</span>
  </div>
  <pre><code>export function foo() {}</code></pre>
</div>
```

优先保留：

- 语言
- 文件名
- 落点片段

## 表格

适用：

- 文件改动表
- 按钮规则表
- 状态对照表
- 记录类型表

建议使用带包裹层的表格：

```html
<div class="tbl-wrap">
  <table>...</table>
</div>
```

## Badge

适用：

- 新增
- 收尾
- 改动量大
- 颜色语义

```html
<span class="badge badge-amber">新增</span>
<span class="badge badge-red">改动量大，优先启动</span>
```

不要把 badge 用成纯装饰标签。

## Card Grid

适用：

- 并列动作说明
- 多种方案状态
- 不同弹窗 / ActionSheet 的结构差异

```html
<div class="card-grid">
  <div class="card">
    <h4>complete</h4>
    <p>标题 + 描述 + 确认按钮</p>
  </div>
</div>
```

## Callout

适用：

- 待确认
- 提示
- 设计师确认中
- 说明性提醒

```html
<div class="callout">待 UI 设计师最终确认筛选栏布局。</div>
<div class="callout info">这里只记录联调契约，后端实现另行处理。</div>
```

## Steps

适用：

- 实施顺序
- 推进节奏
- 多端排期建议

```html
<ol class="steps">
  <li><div><strong>Mobile 端</strong></div></li>
  <li><div><strong>Admin 端</strong></div></li>
</ol>
```

## 目录高亮脚本

这个风格允许轻量功能脚本，用来高亮当前目录项。

适用：

- 长规格文档
- 左侧固定目录

不适用：

- 只含 2-3 节的短文档

## 建议语气

- 更像产品设计规格说明
- 更像研发协作文档
- 不像博客
- 不像汇报稿
