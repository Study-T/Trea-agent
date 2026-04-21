# Requirement Context Recorder Protocol
# 需求上下文记录协议

This protocol defines how to record requirement processing context throughout the PM → RD → QA workflow.
本协议定义了在 PM → RD → QA 工作流中如何记录需求处理上下文。

## Important: Daily Context Logging
## 重要：每日上下文记录

**Daily work logs are stored in `core/context-log/logs/` — ONE FILE PER DAY!**
**日常工作日志存储在 `core/context-log/logs/`——每天一个新文件！**

- `core/context-log/logs/YYYY-MM-DD.md`
- `core/context-log/logs/2026-04-19.md` (example / 示例)

See `core/context-log/SKILL.md` for full details on daily logging.
详细的每日日志记录规则请参阅 `core/context-log/SKILL.md`。

## Recording Triggers
## 记录触发条件

Recording happens at these precise moments:
记录发生在以下精确时刻：

### PM Phase Complete
### PM阶段完成
- **Trigger**: PM Leader completes review AND Boss approves AND user confirms OK
- **触发**: PM组长完成审核 **且** Boss通过审核 **且** 用户确认 OK
- **Recorder Action**: Record to today's `core/context-log/logs/YYYY-MM-DD.md`
- **记录者动作**: 记录到今天的 `core/context-log/logs/YYYY-MM-DD.md`

### RD Phase Complete
### RD阶段完成
- **Trigger**: RD Leader completes review AND Boss approves AND user confirms OK
- **触发**: RD组长完成审核 **且** Boss通过审核 **且** 用户确认 OK
- **Recorder Action**: Record to today's `core/context-log/logs/YYYY-MM-DD.md`
- **记录者动作**: 记录到今天的 `core/context-log/logs/YYYY-MM-DD.md`

### QA Phase Complete
### QA阶段完成
- **Trigger**: QA Leader completes review AND Boss approves AND user confirms OK
- **触发**: QA组长完成审核 **且** Boss通过审核 **且** 用户确认 OK
- **Recorder Action**: Record to today's `core/context-log/logs/YYYY-MM-DD.md`
- **记录者动作**: 记录到今天的 `core/context-log/logs/YYYY-MM-DD.md`

### Requirement Complete
### 需求完成
- **Trigger**: All three phases (PM → RD → QA) have passed Boss approval AND user confirms final output
- **触发**: 三个阶段（PM → RD → QA）全部通过Boss审核 **且** 用户确认最终输出
- **Recorder Action**: Record to today's `core/context-log/logs/YYYY-MM-DD.md`
  - Put complete requirement summary at the BOTTOM of the log
- **记录者动作**: 在今天的 `core/context-log/logs/YYYY-MM-DD.md` 记录
  - 把完整需求总结放在日志的**最下面**

## Recording Rules
## 记录规则

### Precision Required
### 精确性要求

- **Timestamp**: Record exact date and time for EVERY entry (YYYY-MM-DD HH:MM:SS)
- **时间戳**: 每个条目都要记录精确的日期和时间（YYYY-MM-DD HH:MM:SS）
- **Phase Distinction**: Clearly separate PM / RD / QA content
- **阶段区分**: 清晰区分PM / RD / QA内容
- **Skipped Specialists**: If a specialist was not dispatched by the Leader, explicitly mark their output as "Skipped: [Reason]" instead of leaving it blank.
- **跳过记录**: 如果组长未调度某个专员，必须在日志中明确标记为“Skipped: [原因]”，而不是留白。
- **No Interference**: Each phase's records are independent
- **互不干扰**: 各阶段的记录互相独立

### Content Requirements
### 内容要求

Each phase record must contain:
每个阶段记录必须包含：

1. **Requirement ID**: Unique identifier (e.g., REQ-2026-001)
2. **需求ID**: 唯一标识符
3. **Phase**: Which phase (PM/RD/QA)
4. **阶段**: 哪个阶段
5. **Start Time**: When this phase began
6. **开始时间**: 此阶段何时开始
7. **End Time**: When this phase completed
8. **结束时间**: 此阶段何时完成
9. **Leader Output**: PM/RD/QA Leader's summary
10. **组长输出**: PM/RD/QA组长的总结
11. **Boss Feedback**: Boss's review comments
12. **Boss反馈**: Boss的审核意见
13. **Iteration Count**: How many times this phase was revised
14. **迭代次数**: 此阶段修订了多少次

## Directory Structure
## 目录结构

```
skills/workflow-engine/requirements/    ← Templates and protocol / 模板和协议
├── INDEX.md                         ← All requirements index / 所有需求索引
├── RECORDER_PROTOCOL.md              ← This protocol / 本协议
├── templates/                       ← Recording templates / 记录模板
├── active/                          ← Currently processing / 处理中
│   └── REQ-YYYY-NNN/
│       ├── metadata.md              ← Requirement basic info / 需求基本信息
│       ├── prd.md                   ← PRD document / PRD文档
│       ├── pm-record.md             ← PM phase record / PM阶段记录
│       ├── rd-record.md             ← RD phase record / RD阶段记录
│       ├── qa-record.md             ← QA phase record / QA阶段记录
│       ├── rd/                      ← RD technical docs / RD技术文档
│       │   └── [tech-docs]
│       ├── qa/                      ← QA test reports / QA测试报告
│       │   └── [test-reports]
│       └── timeline.md              ← Full timeline / 完整时间线
└── completed/                       ← Completed requirements / 已完成需求
    └── REQ-YYYY-NNN/
        ├── metadata.md              ← Requirement basic info / 需求基本信息
        ├── prd.md                   ← PRD document / PRD文档
        ├── pm-record.md             ← PM phase record / PM阶段记录
        ├── rd-record.md             ← RD phase record / RD阶段记录
        ├── qa-record.md             ← QA phase record / QA阶段记录
        ├── rd/                      ← RD technical docs / RD技术文档
        │   └── [tech-docs]
        ├── qa/                      ← QA test reports / QA测试报告
        │   └── [test-reports]
        ├── timeline.md              ← Full timeline / 完整时间线
        └── summary.md               ← Final summary / 最终总结

core/context-log/                     ← Daily logs / 每日日志
└── logs/
    ├── YYYY-MM-DD.md              ← One file per day / 每天一个文件
    ├── 2026-04-19.md              ← Example / 示例
    └── ...
```

## Requirement ID Format
## 需求ID格式

```
REQ-YYYY-NNN
```
- **YYYY**: Year (e.g., 2026)
- **NNN**: Sequential number, reset each year (001, 002, ...)
- **示例**: REQ-2026-001, REQ-2026-002

## Daily Log Recording
## 每日日志记录

See `core/context-log/SKILL.md` for full format and rules.
详细格式和规则请参阅 `core/context-log/SKILL.md`。

## Recording Templates
## 记录模板

See templates in `skills/workflow-engine/requirements/templates/`:
请参阅 `skills/workflow-engine/requirements/templates/` 中的模板：

- `TEMPLATE-metadata.md` - Requirement metadata
- `TEMPLATE-prd.md` - PRD document
- `TEMPLATE-pm-record.md` - PM phase record
- `TEMPLATE-rd-record.md` - RD phase record
- `TEMPLATE-qa-record.md` - QA phase record
- `TEMPLATE-timeline.md` - Full timeline
- `TEMPLATE-summary.md` - Final summary
- `TEMPLATE-index.md` - Requirements index
