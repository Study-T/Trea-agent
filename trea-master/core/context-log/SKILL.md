---
name: "context-log"
description: "Automatic context recording system. Records all activities, decisions, and requirement progress. One file per day."
---

# Context Log
# 上下文记录系统

## Purpose
## 用途

This is the automatic context recording system. It records everything you do, making it easy to track progress and maintain continuity across sessions.
这是自动上下文记录系统。它记录你做的一切，方便跟踪进度和保持会话间的连续性。

## Important Rules
## 重要规则

1. **ONE file per day**: Each day has its OWN separate log file (e.g., `2026-04-19.md`, `2026-04-20.md`)
2. **每天一个文件**: 每天都有独立的日志文件（例如 `2026-04-19.md`、`2026-04-20.md`）
3. **Do NOT combine**: Different days' logs are NEVER in the same file
4. **不要合并**: 不同日期的日志绝不能放在同一个文件中
5. **User confirmation required**: Only record after user confirms the output is acceptable
6. **需要用户确认**: 只有在用户确认输出可接受后才记录

## Directory Structure
## 目录结构

```
context-log/
├── SKILL.md              ← This file / 本文件
└── logs/                 ← Daily logs / 每日日志
    └── YYYY-MM-DD.md    ← One file per day / 每天一个文件
```

## Document Storage Locations
## 文档存储位置

Where to store different types of documents:
不同类型文档的存储位置：

| Document Type | Storage Location |
|--------------|-----------------|
| Daily work logs | context-log/logs/YYYY-MM-DD.md |
| 每日工作日志 | context-log/logs/YYYY-MM-DD.md |
| Requirement PRD | workflow-engine/requirements/active/REQ-YYYY-NNN/prd.md |
| 需求PRD文档 | workflow-engine/requirements/active/REQ-YYYY-NNN/prd.md |
| Phase records | workflow-engine/requirements/active/REQ-YYYY-NNN/ |
| 阶段记录 | workflow-engine/requirements/active/REQ-YYYY-NNN/ |
| Technical docs (active) | workflow-engine/requirements/active/REQ-YYYY-NNN/rd/ |
| 技术文档（活跃） | workflow-engine/requirements/active/REQ-YYYY-NNN/rd/ |
| Technical docs (completed) | workflow-engine/requirements/completed/REQ-YYYY-NNN/rd/ |
| 技术文档（完成） | workflow-engine/requirements/completed/REQ-YYYY-NNN/rd/ |
| Test reports (active) | workflow-engine/requirements/active/REQ-YYYY-NNN/qa/ |
| 测试报告（活跃） | workflow-engine/requirements/active/REQ-YYYY-NNN/qa/ |
| Test reports (completed) | workflow-engine/requirements/completed/REQ-YYYY-NNN/qa/ |
| 测试报告（完成） | workflow-engine/requirements/completed/REQ-YYYY-NNN/qa/ |
| Framework evolution | core/meta-skill/EVOLUTION_LOG.md |
| 框架进化记录 | core/meta-skill/EVOLUTION_LOG.md |
| Knowledge base | knowledge/methods/ or knowledge/templates/ |
| 知识库 | knowledge/methods/ 或 knowledge/templates/ |

### Storage Principles
### 存储原则

1. **Active requirements** → `workflow-engine/requirements/active/`
   活跃需求 → 工作流引擎的需求活跃目录

2. **Completed requirements** → `workflow-engine/requirements/completed/`
   已完成需求 → 归档到工作流引擎的需求完成目录

3. **Daily logs** → `context-log/logs/YYYY-MM-DD.md`
   每日日志 → 按日期分离

4. **Framework changes** → `core/meta-skill/EVOLUTION_LOG.md`
   框架变更 → 进化日志

## Recording Trigger
## 记录触发条件

**Record ONLY after user confirms "acceptable" / 只有在用户确认"可以"后才记录**

```
Phase completes → Boss approves → Show to user → User says "OK" → RECORD ★
```

## Daily Log Structure
## 每日日志结构

```markdown
# YYYY-MM-DD Work Log
# YYYY-MM-DD 工作日志

## Phase Records (in order)
## 阶段记录（按顺序）

### [HH:MM:SS] REQ-YYYY-NNN - PM Phase Complete
### [HH:MM:SS] REQ-YYYY-NNN - PM阶段完成
- **Leader approved**: Yes
- **Boss approved**: Yes
- **User confirmed**: Yes
- **PM output summary**: [summary]
- **Boss feedback**: [comments]

### [HH:MM:SS] REQ-YYYY-NNN - RD Phase Complete
### [HH:MM:SS] REQ-YYYY-NNN - RD阶段完成
- **Leader approved**: Yes
- **Boss approved**: Yes
- **User confirmed**: Yes
- **RD output summary**: [summary]
- **Boss feedback**: [comments]

### [HH:MM:SS] REQ-YYYY-NNN - QA Phase Complete
### [HH:MM:SS] REQ-YYYY-NNN - QA阶段完成
- **Leader approved**: Yes
- **Boss approved**: Yes
- **User confirmed**: Yes
- **QA output summary**: [summary]
- **Boss feedback**: [comments]

---

## Complete Requirement Summary (at BOTTOM)
## 完整需求总结（在最下面）

### REQ-YYYY-NNN: [Requirement Title]
### REQ-YYYY-NNN: [需求标题]

- **Completed**: YYYY-MM-DD HH:MM:SS
- **Total Duration**: X hours
- **Status**: ✅ Completed

#### PM Phase
- **Duration**: X hours
- **Iterations**: 1
- **Key Output**: [summary]

#### RD Phase
- **Duration**: X hours
- **Iterations**: 1
- **Key Output**: [summary]

#### QA Phase
- **Duration**: X hours
- **Iterations**: 1
- **Key Output**: [summary]

#### Key Decisions
1. [Decision 1]

#### Challenges & Solutions
| Challenge | Solution |
|-----------|----------|
| [Challenge] | [Solution] |

#### Delivered Artifacts
- [Artifact 1]

#### Final Approval
- **PM Leader approved**: Yes - [comments]
- **RD Leader approved**: Yes - [comments]
- **QA Leader approved**: Yes - [comments]
- **Boss approved**: Yes - [comments]
- **User sign-off**: YYYY-MM-DD HH:MM:SS - "可以" / "OK"
```

## Rules
## 规则

### Recording Rules
### 记录规则

1. **New file each day**: `logs/YYYY-MM-DD.md` - never combine days
2. **每天新文件**: `logs/YYYY-MM-DD.md` - 绝不合并日期
3. **Precise timestamps**: Always record exact time (HH:MM:SS)
4. **精确时间戳**: 始终记录精确时间（时:分:秒）
5. **User confirmation FIRST**: Only record after user approves
6. **用户确认优先**: 只有用户批准后才记录
7. **Summary at BOTTOM**: Put complete summary at the bottom of daily log
8. **总结在最后**: 把完整总结放在每日日志的最下面

## Reading Strategy
## 读取策略

### Context Window
### 上下文窗口

When starting a new session, read recent logs to understand context:
开始新会话时，读取最近的日志以了解上下文：

| Situation | What to Read |
|----------|--------------|
| Quick task | Today's log only |
| Quick task / 快速任务 | 只读今天日志 |
| Ongoing project | Today + yesterday |
| Ongoing project / 进行中项目 | 今天 + 昨天 |
| New requirement | Last 3 days |
| New requirement / 新需求 | 最近3天 |
| Research / investigation | Last 7 days |
| Research / investigation / 研究调查 | 最近7天 |

### Reading Order
### 阅读顺序

1. **Today first**: Start with today's log if exists
2. **今天优先**: 先读今天的日志（如果存在）
3. **Work backward**: Read previous days in reverse chronological order
4. **向前回溯**: 按倒序阅读之前的天数
5. **Skip empty days**: Days with no records can be skipped
6. **跳过空白**: 没有记录的日期可以跳过
7. **Find summaries**: Look for "Complete Requirement Summary" sections
8. **找总结**: 查找"完整需求总结"部分

### What to Extract
### 提取什么

From each log, extract:
从每个日志中提取：

- **Active requirements**: What's currently being worked on
- **进行中需求**: 当前正在处理的需求
- **Recent completions**: What's been finished recently
- **近期完成**: 最近完成的内容
- **Pending items**: What's waiting for user confirmation
- **待处理项**: 等待用户确认的内容
- **Key decisions**: Important choices made
- **关键决策**: 做出的重要选择

### Log Prioritization
### 日志优先级

| Priority | Content | Read Time |
|----------|---------|----------|
| 1 | Today's log | Always |
| 2 | Complete summaries | Always |
| 3 | Recent phase completions | Always |
| 4 | Daily activities | If needed |
| 5 | Method notes | For reference |

| 优先级 | 内容 | 阅读时间 |
|--------|------|----------|
| 1 | 今日日志 | 始终 |
| 2 | 完整总结 | 始终 |
| 3 | 近期阶段完成 | 始终 |
| 4 | 每日活动 | 按需 |
| 5 | 方法笔记 | 参考 |

## Auto-Summary Rule
## 自动摘要规则

At the end of each log file, create a quick summary section:
在每个日志文件末尾，创建快速摘要部分：

```markdown
## Quick Summary / 快速摘要
## YYYY-MM-DD

**Active**: REQ-001 (RD Phase), REQ-002 (PM Phase)
**进行中**: REQ-001 (RD阶段), REQ-002 (PM阶段)

**Completed Today**: REQ-003 (QA Phase)
**今日完成**: REQ-003 (QA阶段)

**Pending**: User confirmation on REQ-001 RD output
**待处理**: 等待用户确认REQ-001 RD产出
```
