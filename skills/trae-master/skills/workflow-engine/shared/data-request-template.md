# Data Request Template
# 数据请求模板

When a specialist lacks required data, use this template to report.
当专员缺少所需数据时，使用此模板报告。

## Specialist Data Missing Output
## 专员数据缺失输出

```
👤 <specialist_role>: ⛔ DATA_MISSING
  📋 需要数据 / Required Data: <description of needed data / 需要的数据描述>
  ❓ 原因 / Reason: <why this data is needed for this specific task / 为什么此任务需要此数据>
  📎 数据格式 / Data Format: <expected data format / 期望的数据格式>
  🔗 依赖来源 / Source: <where this data should come from / 此数据应来自何处 (user/external system/etc. / 用户/外部系统/等)>
```

## Leader Aggregation Format
## 组长汇总格式

When a leader collects all missing data requests from specialists:
当组长收集所有专员的数据缺失请求时：

```
📊 <leader_name> 数据请求汇总 / Data Request Summary
──────────────────────────────
  1. <specialist_1_role>:
     需要数据 / Required: <description / 描述>
     原因 / Reason: <reason / 原因>
     期望格式 / Expected Format: <format / 格式>

  2. <specialist_2_role>:
     需要数据 / Required: <description / 描述>
     原因 / Reason: <reason / 原因>
     期望格式 / Expected Format: <format / 格式>
──────────────────────────────
📤 上报给 / Report to: 老板 / Boss
```

## Rules
## 规则

- A specialist MUST stop immediately when data is missing — do NOT guess or fabricate data / 专员在数据缺失时必须立即停止——不得猜测或编造数据
- The leader MUST collect ALL missing data requests before reporting to Boss / 组长必须在报告给Boss前收集所有数据缺失请求
- Boss MUST output the complete list to the user / Boss必须将完整列表输出给用户
- Flow resumes ONLY after the user provides the requested data / 流程仅在用户提供所需数据后恢复
- If the user cannot provide the data, the specialist must note it as "UNAVAILABLE" and proceed with assumptions clearly marked / 如果用户无法提供数据，专员必须标记为"UNAVAILABLE"并在明确标注假设的情况下继续
