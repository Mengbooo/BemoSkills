# Component Map

这个 skill 不是把 Markdown 标签逐个翻译成 HTML 标签，而是把“文档意图”翻译成稳定组件。

## 目录与章节

- Markdown `#`：页面总标题，对应 `<h1>`
- Markdown `##`：一级章节，同时进入左侧目录，对应 `<h2 id="sec-n">`
- Markdown `###`：章节内子主题，对应 `<h3>`
- Markdown `####`：更细层级，对应 `<h4>`

目录建议使用：

```html
<aside class="toc-sidebar">
  <nav class="toc">
    <div class="toc-title">目录</div>
    <ol>
      <li><a href="#sec-1">总体结论</a></li>
      <li><a href="#sec-2">完成时间线</a></li>
    </ol>
  </nav>
</aside>
```

## 总结块

适用：

- 总体结论
- 接手提示
- 一段需要读者先抓住的大意

```html
<div class="callout">
  这里放总结性结论、核心判断或接手提示。
</div>
```

## 风险块

适用：

- 待优化
- 已知限制
- 风险说明
- 不可逆操作警告

```html
<div class="callout callout-warn">
  <strong>待确认：</strong>这里放风险、约束或警告信息。
</div>
```

## 说明块

适用：

- 背景说明
- 配置说明
- 阅读提示

```html
<div class="callout callout-tip">
  <strong>提示：</strong>这里放非阻断性的说明。
</div>

<div class="callout callout-info">
  <strong>说明：</strong>这里放中性解释。
</div>
```

## 流程块

适用：

- 启动链路
- 构建链路
- 命令展开流程
- 目录树但希望更强调“执行路径”

```html
<div class="flow-box">pnpm run docker:up
└─ scripts/docker-up.sh local
   ├─ 1. 读取 .env
   ├─ 2. 构建后端
   └─ 3. docker compose up -d --build</div>
```

如果只是普通代码或日志，不要强行用 `flow-box`，继续使用 `pre > code`。

## 表格

默认保持简单：

```html
<table>
  <thead>
    <tr><th>项目</th><th>状态</th><th>说明</th></tr>
  </thead>
  <tbody>
    <tr><td>Gateway</td><td class="pass">通过</td><td>HTTP 200</td></tr>
  </tbody>
</table>
```

对“通过 / 成功 / 正常”这种状态值，可加 `class="pass"`。

## FAQ

适用：

- 常见问题排查
- 问答式手册

```html
<div class="qa">
  <p class="qa-q">Q1：构建失败怎么办？</p>
  <p><strong>现象</strong>：这里描述现象。</p>
  <pre><code>pnpm run build</code></pre>
</div>
```

## 建议样式语气

- 整体偏安静、理性、文档感
- 不追求炫技
- 强调长期阅读和交接，而不是一次性展示
- 用少量蓝色 / 黄色提示信息，不做多彩仪表盘

## 什么时候可以直接保留 Markdown 语义

这些内容通常直接对应 HTML 标签即可：

- 普通段落
- 无序列表
- 有序列表
- 代码块
- 引用的命令与日志

## 什么时候应该升级为组件

这些内容若继续当普通段落，信息价值会下降：

- 结论
- 风险
- 说明
- 排障问答
- 执行流程
- 验证状态
