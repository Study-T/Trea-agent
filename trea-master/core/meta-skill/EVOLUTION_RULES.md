# Evolution Rules
# 进化规则

## Trigger Conditions
## 触发条件

**自动进化仅在用户整体任务完成后触发，任务执行过程中不进行进化。**

任务完成后，AI通过进化分析检查清单发现问题，则触发进化：

| # | 问题类型 | 说明 |
|---|---------|------|
| 1 | 数据真实性问题 | 任务过程中出现推断/推测/预测的虚假数据 |
| 2 | 流程执行问题 | 框架流程未被正确执行，有遗漏步骤 |
| 3 | 日志记录问题 | 阶段完成后未自动记录日志 |
| 4 | 代码优先问题 | RD阶段未先查代码就设计方案 |
| 5 | Boss审核问题 | Boss审核未正确拦截不合格产出 |
| 6 | 专员调度问题 | 专员调度不合理，有冗余或缺失 |
| 7 | 用户纠正问题 | 用户需要多次纠正AI行为 |
| 8 | 工具使用问题 | 未充分利用可用工具 |

**没有发现问题 → 不进行进化**

## Evolution Timing
## 进化时机

```
用户整体任务完成
        ↓
Step 1: 日志总结
  - 回顾整个任务过程
  - 记录到 context-log
  - 记录到阶段 record 文件
        ↓
Step 2: 进化分析
  - 逐项检查进化分析检查清单
  - 识别任务过程中出现的问题
        ↓
Step 3: 判断
  - 有问题 → 生成进化提案 → 展示给用户 → 用户决定
  - 没有问题 → 不进行进化 → 任务结束
```

## Proposal Rules
## 提案规则

1. **One proposal at a time**
   一次只提一个提案

2. **Clear problem statement**
   问题描述清晰

3. **Specific solution**
   解决方案具体

4. **Impact assessment included**
   包含影响评估

5. **User-friendly presentation**
   用户友好的呈现方式

6. **Only after task completion**
   仅在任务完成后提议

## Approval Process
## 审批流程

```
任务完成 → 日志总结 → 进化分析 → 发现问题
        ↓
AI生成进化提案
        ↓
展示给用户
        ↓
用户批准 → AI执行修改 → 记录进化日志
用户拒绝 → 记录原因，不修改
```

## Execution Rules
## 执行规则

1. **Backup before change**
   变更前先备份

2. **Follow proposal exactly**
   严格按照提案执行

3. **Update evolution log**
   更新进化日志

4. **Test if possible**
   尽量测试

5. **Report to user**
   向用户汇报结果

6. **No evolution without problem**
   没有问题不进化
