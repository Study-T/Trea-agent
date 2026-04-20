# Acceptance Criteria
# 验收标准

## Purpose
## 目的

Define what qualifies as "done" for each phase.
定义每个阶段"完成"的标准。

## Phase Completion Standards
## 各阶段完成标准

### PM Phase
### PM阶段

| Item | Criteria |
|------|----------|
| PRD Document | Complete with user personas, requirements, acceptance criteria |
| PRD文档 | 包含用户画像、需求、验收标准 |
| PM Leader Review | PM Leader reviews and approves all specialist outputs |
| PM组长审核 | PM组长审核通过所有专员输出 |
| Technical Feasibility | Boss reviews and PM Leader confirms feasibility based on initial analysis |
| 技术可行性 | Boss审核，PM组长基于初步分析确认可行性 |
| Timeline | Explicit milestone dates defined |
| 时间线 | 明确里程碑日期 |

### RD Phase
### RD阶段

| Item | Criteria |
|------|----------|
| Code Implementation | Code matches PRD requirements |
| 代码实现 | 代码符合PRD需求 |
| RD Leader Review | RD Leader reviews and approves all specialist outputs |
| RD组长审核 | RD组长审核通过所有专员输出 |
| Boss Review | Boss reviews and approves the complete RD output |
| Boss审核 | Boss审核通过RD全部产出 |
| Unit Tests | Core functions have test coverage |
| 单元测试 | 核心功能有测试覆盖 |
| Documentation | API docs and README updated |
| 文档 | API文档和README已更新 |

### QA Phase
### QA阶段

| Item | Criteria |
|------|----------|
| Test Cases | All scenarios covered |
| 测试用例 | 覆盖所有场景 |
| QA Leader Review | QA Leader reviews and approves all specialist outputs |
| QA组长审核 | QA组长审核通过所有专员输出 |
| Boss Review | Boss reviews and approves the complete QA output |
| Boss审核 | Boss审核通过QA全部产出 |
| Test Execution | All test cases passed |
| 测试执行 | 所有测试用例通过 |
| Bug Fixes | All critical/high bugs resolved |
| 缺陷修复 | 所有高/严重缺陷已解决 |
| Test Report | Test summary report delivered |
| 测试报告 | 测试摘要报告已交付 |

## Approval Flow
## 审批流程

Each phase must go through the following approval chain:
每个阶段必须经过以下审批链：

```
Phase completes
阶段完成
        ↓
[PM/RD/QA] Leader reviews and approves
[PM/RD/QA]组长审核通过
        ↓
Boss reviews and approves
Boss审核通过
        ↓
Show output to user
展示输出给用户
        ↓
User confirms "OK"
用户确认"OK"
        ↓
Record to context-log
记录到context-log
```

## Retry and Failure Handling
## 重试与失败处理

### Retry Rules
### 重试规则

| Attempt | Boss Action |
|---------|-------------|
| 1st rejection | Return to current leader with error package |
| 第1次拒绝 | 附带错误包返回给当前组长 |
| 2nd rejection | Return again with more specific feedback |
| 第2次拒绝 | 再次返回，提供更具体的反馈 |
| 3rd rejection | Final warning - must fix before proceeding |
| 第3次拒绝 | 最后警告 - 必须修复才能继续 |

### After 3 Rejections
### 3次拒绝后

When 3 rejections are reached:
当达到3次拒绝时：

```
⚠️ Max Rejections Reached / 达到最大拒绝次数
        ↓
Boss offers options to user:
Boss向用户提供选项：
```

| Option | Description |
|--------|-------------|
| Retry | Restart this phase from beginning / 从头重启本阶段 |
| Skip | Skip this requirement, move to next / 跳过本需求，继续下一个 |
| Simplify | Reduce scope to fit constraints / 缩减范围以适应限制 |
| Abort | Stop workflow, record failure / 停止工作流，记录失败 |

### Failure Record
### 失败记录

When a phase fails (user chooses Abort or cannot proceed):
当阶段失败时（用户选择Abort或无法继续）：

```markdown
## Phase Failure Record / 阶段失败记录
- **Phase**: [PM/RD/QA]
- **Rejections**: 3
- **Final Rejection Reason**: [reason]
- **Last Attempt Date**: YYYY-MM-DD HH:MM:SS
- **User Decision**: [Retry/Skip/Simplify/Abort]
- **Alternative**: [if Skip or Simplify chosen]
```

All failures must be recorded in context-log.
所有失败必须记录到context-log。

## Delivery Checklist
## 交付检查清单

### Before Delivery
### 交付前

- [ ] Phase output meets completion standards
- [ ] 阶段产出符合完成标准
- [ ] Leader approved
- [ ] 组长审核通过
- [ ] Boss approved
- [ ] Boss审核通过
- [ ] Output shown to user
- [ ] 输出已展示给用户
- [ ] User confirmed "OK"
- [ ] 用户确认"OK"
- [ ] Recorded to context-log
- [ ] 已记录到context-log

### Final Acceptance
### 最终验收

- [ ] All phase criteria met
- [ ] 所有阶段标准已满足
- [ ] All Boss approvals obtained
- [ ] 所有Boss审批已获得
- [ ] User sign-off received
- [ ] 用户签字确认
- [ ] Documentation archived
- [ ] 文档已归档
