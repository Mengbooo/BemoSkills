# structured-ai-dev-workflow

## 中文名

AI 结构化开发闭环

## 定位

当用户交给 AI 一个开发需求时，先把需求、现状、方案、任务、提交和复盘固化成一套可追踪的工程闭环，避免直接改代码导致上下文丢失、范围失控或后续难以接手。

适合：

- 中大型功能开发
- 涉及前后端、数据模型、接口契约或多模块协作的需求
- 用户希望先 research 再 plan 再实现
- 用户希望按 phase 交付、验证、commit
- 需要沉淀 worklog，方便后续 AI 或人类接着工作

不适合：

- 一两行的小修复
- 单纯解释代码
- 用户明确要求直接修改且时间成本比流程收益更高的任务

## 工作目录

默认在仓库根目录创建或复用 `.docs/`：

```text
.docs/
  demands/      # 原始需求、用户输入、PRD、截图说明、补充口径
  research/     # 需求拆解 + 现有实现盘点 + 差距和风险
  plans/        # 技术方案、边界、关键决策、接口契约、验收口径
  task/         # 按功能或方向拆分的 phase 任务
  worklog/      # 每个 phase 完成后的实现日志、验证记录和下一步
```

如果项目已有等价目录，优先沿用现有结构。不要为了套模板迁移用户已有文档。

## 流程

### 1. Demand

把用户需求先沉淀到 `.docs/demands/`。

要求：

- 保留原始表达，不要过度改写。
- 如果需求来自截图、HTML 原型、聊天记录或外部文档，记录来源。
- 标注日期、主题、适用端或模块。
- 明确哪些内容是用户确认过的，哪些只是 AI 推断。

小需求可以直接在 research 开头引用用户需求，不强制单独建 demand 文件。

### 2. Research

在 `.docs/research/` 中完成需求和现有实现盘点。

必须包含：

- 研究范围：本轮只看什么，不看什么。
- 需求拆解：用户真正要的行为、数据、交互、状态和边界。
- 现有实现盘点：入口、模块、类型、接口、数据模型、测试、配置。
- 差距分析：哪些能复用，哪些需要改，哪些不能碰。
- 风险和疑问：需要用户确认或实现时重点验证的内容。
- 初步建议：推荐路线，但不要在 research 里写成最终计划。

盘点现有实现时必须引用真实文件路径和关键位置。不要只凭猜测写结论。

### 3. Plan

在 `.docs/plans/` 中写实现计划。

必须包含：

- 目标：本轮要达成的用户可感知结果。
- 范围边界：包含什么、不包含什么。
- 关键决策：技术路线、数据口径、接口契约、兼容策略。
- 改动点：按模块列出预期改动。
- 验收口径：可验证的行为标准。
- 风险与约束：实现时最容易出错的地方。

Plan 负责“为什么这么做”和“做到什么算完成”。不要把每个文件的机械操作塞进 plan。

### 4. Task

在 `.docs/task/<feature-slug>/` 中按 phase 生成任务。

命名建议：

```text
00-phase-0-contract-and-decisions.md
01-phase-1-data-model.md
02-phase-2-service-and-query.md
03-phase-3-ui-or-api.md
04-phase-4-tests-and-handoff.md
```

每个 phase 必须包含：

- 目标
- 任务清单
- 预期改动范围
- 验收标准
- 依赖关系
- 不做事项

Phase 应该可独立验证、可独立 commit。不要把一个无法验证的大包塞进一个 phase。

### 5. Implement And Commit

执行时一次只推进一个 phase。

每个 phase 的节奏：

1. 读取对应 task。
2. 检查 git 状态，识别用户已有改动。
3. 实现该 phase 的最小闭环。
4. 运行与改动风险匹配的验证。
5. 更新或创建 worklog。
6. 只提交本 phase 相关文件。

提交信息建议：

```text
feat(scope): complete phase N for <feature>
fix(scope): address phase N issue for <feature>
docs(workflow): add <feature> plan and tasks
```

不要回滚用户未要求回滚的改动。提交前必须确认 staged 文件只包含本阶段相关内容。

### 6. Worklog

每个 phase 完成后，在 `.docs/worklog/` 创建记录。

必须包含：

- 本阶段完成内容
- 重点 review 位置
- 改动文件
- 验证命令和结果
- 未完成事项或下一阶段注意点
- commit hash，如果已经提交

Worklog 是给后续 AI 和人类接手用的工程记忆，不是流水账。要写清为什么这样改，以及后续最应该看哪里。

## 模式选择

### 轻量模式

用于小到中等需求：

- demand 可以合并到 research。
- research 和 plan 可以写在同一份文档中，但必须保留现状盘点和验收口径。
- task 可以只有 1-2 个 phase。
- worklog 仍然要写。

### 完整模式

用于中大型需求：

- 独立 demand、research、plan。
- 前端、后端或不同子系统可以拆分 plan。
- task 按 phase 拆分到独立文件。
- 每个 phase 独立验证、独立 commit、独立 worklog。

## 文档命名

建议使用：

```text
.docs/demands/<feature-slug>-demand-YYYYMMDD.md
.docs/research/<feature-slug>-research-YYYYMMDD.md
.docs/plans/<feature-slug>-plan-YYYYMMDD.md
.docs/task/<feature-slug>/NN-phase-N-<topic>.md
.docs/worklog/<feature-slug>-phase-N-YYYYMMDD.md
```

如果项目已有命名习惯，优先保持一致。

## 质量标准

- Research 必须基于真实代码盘点。
- Plan 必须有明确边界和验收口径。
- Task 必须能指导 AI 直接执行。
- Phase 必须可验证、可提交。
- Worklog 必须能帮助下一轮恢复上下文。
- Commit 必须小而清晰，避免混入无关变更。

## 常用提示词

开始新需求：

```text
按 structured-ai-dev-workflow 处理这个需求：先沉淀 demand，再 research 现有实现，然后写 plan 和 phased task，等我确认后再开始实现。
```

直接进入实现：

```text
按 .docs/task/<feature>/ 的 phase 顺序实现。每完成一个 phase，验证、commit，并写 worklog。
```

接续已有工作：

```text
读取 .docs/research、.docs/plans、.docs/task 和最新 worklog，判断当前做到哪个 phase，然后继续下一阶段。
```
