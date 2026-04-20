# Self-Evolution Mechanism
# 自我进化机制

## Purpose
## 目的

Allow the framework to improve itself through use.
让框架在使用过程中不断自我优化。

## Core Principle
## 核心原则

1. **任务完成后进化**：自动进化仅在用户整体任务完成后进行，任务执行过程中不进行进化
2. **问题驱动进化**：只有发现问题时才进化，没有问题不进化
3. **AI提议，用户决定**：AI可以发现问题并提出改进建议，但必须经用户批准后才能修改

## Evolution Timing
## 进化时机

```
用户整体任务完成（所有阶段结束或用户终止任务）
        ↓
日志总结：回顾整个任务过程，记录到context-log
        ↓
自动进化分析：检查任务过程中是否发现问题
        ↓
    ┌─── 有问题 ───┐
    │              │
    ▼              ▼
 生成进化提案   向用户汇报进化提案
    │              │
    │         用户批准 → 执行修改 → 记录进化日志
    │         用户拒绝 → 记录原因，不修改
    │
    └─── 没有问题 ───┘
           │
           ▼
      不进行进化，任务结束
```

## Evolution Analysis Checklist
## 进化分析检查清单

任务完成后，AI必须逐项检查以下内容：

| # | 检查项 | 说明 |
|---|--------|------|
| 1 | 数据真实性 | 任务过程中是否出现推断/推测/预测的虚假数据？ |
| 2 | 流程执行 | 框架流程是否被正确执行？是否有遗漏步骤？ |
| 3 | 日志记录 | 每个阶段完成后是否自动记录了日志？ |
| 4 | 代码优先 | RD阶段是否先查代码再设计方案？ |
| 5 | Boss审核 | Boss审核是否正确拦截了不合格产出？ |
| 6 | 专员调度 | 专员调度是否合理？是否有冗余或缺失？ |
| 7 | 用户交互 | 是否需要用户多次纠正？ |
| 8 | 工具使用 | 是否充分利用了可用工具（MCP/搜索/读取）？ |

**如果以上所有检查项均无问题 → 不进行进化**
**如果发现任何问题 → 生成进化提案，展示给用户**

## What Can Be Evolved
## 可进化内容

| Category | Examples |
|----------|---------|
| New skill added | 发现缺少某个skill |
| Rule improved | 调度规则/通信规则需要调整 |
| Process optimized | 工作流程需要改进 |
| Knowledge base | 知识库需要补充 |
| Template updated | 模板需要优化 |

## What Cannot Be Evolved
## 不可进化内容

- User decisions (user confirmations)
  用户确认结果
- Final deliverables
  最终交付物
- Context-log records
  上下文日志记录

## Evolution Proposal Template
## 进化提案模板

```markdown
## 框架优化建议提案 / Framework Optimization Proposal

### 问题描述 / Problem Description
[AI发现的问题]

### 原因分析 / Root Cause Analysis
[为什么会产生这个问题]

### 优化建议 / Optimization Suggestion
[具体的改进方案]

### 预期效果 / Expected Outcome
[改进后能达到的效果]

### 影响范围 / Impact Scope
[会影响哪些部分]
```

## Safety Rules
## 安全规则

1. AI proposes, user decides
   AI提议，用户决定

2. All changes must be recorded
   所有变更必须记录

3. Original version must be kept before modification
   修改前必须保留原版本

4. Evolution log must be updated
   进化日志必须更新

5. Evolution only happens after task completion, never during task execution
   进化仅在任务完成后进行，任务执行过程中不进化

6. No problem found = no evolution
   没有发现问题 = 不进行进化
