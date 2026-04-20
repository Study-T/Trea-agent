# Skill Communication Protocol
# 技能通信协议

## Purpose
## 目的

Define how skills exchange data when working together.
定义技能协作时的数据交换方式。

## Data Exchange Principles
## 数据交换原则

1. **Explicit Output / 明确输出** - Each skill must clearly state its output
   每个技能必须清楚说明其输出

2. **Structured Format / 结构化格式** - Use standard formats for data exchange
   使用标准格式进行数据交换

3. **No Hidden State / 无隐藏状态** - All data must be documented
   所有数据必须被记录

## Communication Hierarchy
## 通信层级

All communication must follow the dispatch rules defined in `core/dispatch-rules.md`.
所有通信必须遵循 `core/dispatch-rules.md` 中定义的调度规则。

```
Boss ←→ 组长 ←→ 同组专员
  ↑
用户（需求和数据）
```

See "Skill-to-Skill Communication" section below for format templates.
格式模板请参阅下方"技能间通信"部分。

## Standard Data Formats
## 标准数据格式

### Requirement Format
### 需求格式

```markdown
## Requirement / 需求
- **ID**: REQ-YYYY-NNN
- **Title**: [title]
- **Priority**: High / Medium / Low
- **Description**: [description]
- **Acceptance Criteria**: [list]
```

### Output Format
### 输出格式

```markdown
## Output / 输出
- **Skill**: [skill name]
- **Timestamp**: YYYY-MM-DD HH:MM:SS
- **Type**: [data/decision/artifact]
- **Content**: [content]
- **Next Steps**: [optional]
```

### Decision Format
### 决策格式

```markdown
## Decision / 决策
- **Decision**: [what was decided]
- **Rationale**: [why this decision]
- **Alternatives Considered**: [other options]
- **Approved By**: [who approved]
```

## Skill-to-Skill Communication
## 技能间通信

### Phase Handoff
### 阶段交接

When a phase completes and needs to hand off to the next phase:
当一个阶段完成需要交接给下一个阶段时：

```markdown
## Handoff / 交接
- **From**: [Phase] Leader
- **To**: Boss
- **Request**: [Phase] complete, hand off to [Next Phase]
- **Data**:
  - Requirement ID: REQ-XXX
  - Phase output: [summary]
  - Next action required: [what needs to be done]
```

### Within-Phase Communication (Direct)
### 阶段内通信（直接）

Specialists within the same group can exchange data directly:
同组专员可以直接交换数据：

```markdown
## Internal Exchange / 内部交换
- **From**: [Specialist A]
- **To**: [Specialist B]
- **Data**: [content]
- **Purpose**: [why this exchange]
```

## Data Storage
## 数据存储

| Data Type | Storage | Access |
|-----------|---------|--------|
| Daily work logs | context-log/logs/YYYY-MM-DD.md | All skills |
| Requirement PRD | workflow-engine/requirements/active/REQ-YYYY-NNN/prd.md | All skills |
| Phase records | workflow-engine/requirements/active/REQ-YYYY-NNN/ | All skills |
| Technical docs (active) | workflow-engine/requirements/active/REQ-YYYY-NNN/rd/ | RD only |
| Technical docs (completed) | workflow-engine/requirements/completed/REQ-YYYY-NNN/rd/ | RD only |
| Test reports (active) | workflow-engine/requirements/active/REQ-YYYY-NNN/qa/ | QA only |
| Test reports (completed) | workflow-engine/requirements/completed/REQ-YYYY-NNN/qa/ | QA only |
| Framework evolution | core/meta-skill/EVOLUTION_LOG.md | All skills |
| Method Notes | knowledge/methods/ | All skills |

See `core/context-log/SKILL.md` for complete document storage location details.
完整文档存储位置请参阅 `core/context-log/SKILL.md`。

**Storage Principles / 存储原则:**
- Active requirements → `workflow-engine/requirements/active/`
- Completed requirements → `workflow-engine/requirements/completed/`

## Example Handoff
## 交接示例

### Example 1: PM to RD Handoff
### 示例1：PM到RD交接

PM Leader → Boss → RD Leader:
PM组长 → Boss → RD组长：

```markdown
## Handoff / 交接
- **From**: PM Leader
- **To**: Boss
- **Request**: PM phase complete, hand off to RD
- **Data**:
  - Requirement: REQ-2026-001
  - PM Output Summary:
    - PRD document completed
    - User personas defined
    - Market analysis done
  - RD Action Required:
    - Technical feasibility analysis
    - Architecture design
```

### Example 2: RD to QA Handoff
### 示例2：RD到QA交接

RD Leader → Boss → QA Leader:
RD组长 → Boss → QA组长：

```markdown
## Handoff / 交接
- **From**: RD Leader
- **To**: Boss
- **Request**: RD phase complete, hand off to QA
- **Data**:
  - Requirement: REQ-2026-001
  - Deliverable:
    - Login API implemented
    - Unit tests written
    - Documentation updated
  - QA Action Required:
    - Design test cases
    - Execute integration tests
```

## Rules
## 规则

1. **All cross-phase handoffs go through Boss**
   所有跨阶段交接必须通过Boss中转

2. **Use standard formats** for all data exchange
   使用标准格式进行所有数据交换

3. **Include context** when handing off
   交接时包含上下文

4. **Confirm receipt** when receiving handoff
   接收交接时确认

5. **Record all handoffs** in context-log
   在context-log中记录所有交接
