# Code Review Checklist Template
# 代码审查清单模板

## Review Info / 审查信息
- **PR / MR Link**: [URL]
- **Author / 作者**: [Name]
- **Reviewer / 审查人**: [Name]
- **Date / 日期**: YYYY-MM-DD
- **Description / 描述**: [Brief description of changes]

## Review Checklist / 审查清单

### Functionality / 功能性
- [ ] Code implements the requirement correctly
- [ ] Edge cases are handled
- [ ] Error handling is appropriate
- [ ] No dead code or commented-out logic

### Code Quality / 代码质量
- [ ] Code follows project coding standards
- [ ] Naming conventions are consistent
- [ ] Functions/methods are not too long
- [ ] No code duplication (DRY principle)
- [ ] Comments are meaningful and necessary

### Security / 安全性
- [ ] No hardcoded secrets or credentials
- [ ] Input validation is in place
- [ ] SQL injection prevention
- [ ] Authentication/authorization checks present

### Performance / 性能
- [ ] No N+1 query issues
- [ ] Appropriate data structures used
- [ ] Caching considered where needed
- [ ] No unnecessary loops or recursive calls

### Testing / 测试
- [ ] Unit tests cover core logic
- [ ] Test cases cover edge cases
- [ ] Tests are independent and repeatable
- [ ] Mock data is realistic

### Compatibility / 兼容性
- [ ] Changes are backward compatible
- [ ] API versioning considered
- [ ] i18n/l10n considered if applicable

## Review Result / 审查结果
- **Verdict / 结论**: [Approve / Request Changes / Reject]
- **Summary / 总结**: [Brief summary of review findings]

## Issues Found / 发现的问题
| # | Severity | Description | Line | Suggestion |
|---|----------|-------------|------|------------|
| 1 | [Critical/Major/Minor] | [Description] | [Line] | [Suggestion] |
