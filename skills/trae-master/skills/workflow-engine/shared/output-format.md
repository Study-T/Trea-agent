# Output Format
# 输出格式

Standard output format for all workflow participants.
所有工作流参与者的标准输出格式。

## Boss Output
## Boss输出

```
👔 老板收到需求 / Boss received requirement: <requirement text / 需求文本>
📋 老板理解 / Boss interpretation: <interpreted requirement / 解读后的需求>
➡️ 老板分配给 / Boss assigns to: <leader name / 组长名称>
```

## Leader Output
## 组长输出

```
📌 [<phase>阶段 / Phase] <leader_name>分析拆解任务，分发给专员 / analyzes and distributes tasks to specialists
──────────────────────────────
```

## Specialist Output
## 专员输出

```
👤 <specialist_role>: <work result / 工作结果>
```

## Phase Summary
## 阶段摘要

```
📊 [<phase>阶段 / Phase] 执行摘要 / Execution Summary
  专员数量 / Specialist Count: <count / 数量>
  执行状态 / Status: <completed / 已完成>
  组长审核 / Leader Review: ✅通过 / Approved / ❌不通过 / Rejected
  老板审核 / Boss Review: ✅通过 / Approved / ❌不通过 / Rejected
  用户确认 / User Confirmation: ✅确认 / Confirmed / ❌待确认 / Pending
```

## User Confirmation
## 用户确认

```
👤 用户确认 / User confirmed: "可以" / "OK"
📅 确认时间 / Confirmation time: YYYY-MM-DD HH:MM:SS
```

## Completion Output
## 完成输出

```
🎉🎉🎉 需求全流程完成！所有阶段审核通过！ / Requirement workflow complete! All phases passed review! 🎉🎉🎉
```

## Failure Output
## 失败输出

```
⚠️ [<phase>阶段 / Phase] 达到最大重试次数(3次)，流程终止 / Max retries (3) reached, workflow terminated
📦 最终未通过原因 / Final rejection reason: <reasons / 原因>
```
