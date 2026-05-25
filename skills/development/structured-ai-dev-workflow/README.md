# AI 结构化开发闭环

这是一个给 AI 编程代理使用的开发流程 skill，用来把需求开发拆成可追踪、可验证、可接续的工程闭环。

核心路径：

```text
demand -> research -> plan -> phased task -> implement/commit -> worklog
```

## 为什么需要它

AI 很擅长快速改代码，但在长期项目里容易出现几个问题：

- 没保存原始需求，后续不知道为什么这么改。
- 没盘点现有实现，容易绕开已有架构另起炉灶。
- 没有明确边界，改动范围会扩散。
- 一次改太多，review 和回滚都困难。
- 做完没有 worklog，下一轮 AI 接手又要重新考古。

这个 skill 的目标不是增加文档负担，而是让 AI 先理解系统，再按阶段交付，并留下可恢复的工程记忆。

## 推荐目录

在项目根目录使用 `.docs/`：

```text
.docs/
  demands/      # 原始需求
  research/     # 需求拆解与现有实现盘点
  plans/        # 技术方案与验收口径
  task/         # 分 phase 的执行任务
  worklog/      # 每个 phase 完成后的记录
```

## 每一步产物

`demand`：保存用户原始需求、来源、日期、模块范围。

`research`：拆解需求，盘点现有代码、接口、模型、测试和差距。这里必须引用真实文件，不能靠猜。

`plan`：确定目标、边界、关键决策、接口契约、风险和验收标准。

`task`：把计划拆成可独立验证、可独立提交的 phase。

`worklog`：记录每个 phase 实际完成了什么、改了哪些文件、怎么验证、下一步注意什么。

## 两种使用模式

轻量模式适合小需求：

- demand 可以并入 research。
- research 和 plan 可以合并。
- task 可以只有 1-2 个 phase。
- worklog 仍然保留。

完整模式适合中大型需求：

- demand、research、plan 独立。
- 前后端或多个子系统可以拆成不同 plan。
- 每个 phase 独立任务、独立验证、独立 commit、独立 worklog。

## 常用提示

新需求从头开始：

```text
按 structured-ai-dev-workflow 处理这个需求：先沉淀 demand，再 research 现有实现，然后写 plan 和 phased task，等我确认后再开始实现。
```

已有任务继续实现：

```text
读取 .docs/research、.docs/plans、.docs/task 和最新 worklog，判断当前做到哪个 phase，然后继续下一阶段。
```

按阶段开发并提交：

```text
按 .docs/task/<feature>/ 的 phase 顺序实现。每完成一个 phase，验证、commit，并写 worklog。
```

## 关键原则

- 先盘点现有实现，再写方案。
- Plan 写决策和边界，Task 写可执行动作。
- 每个 phase 都应该可验证、可 commit。
- Worklog 写给下一轮接手的人和 AI。
- 小需求不要被流程压重，中大型需求不要跳过 research。
