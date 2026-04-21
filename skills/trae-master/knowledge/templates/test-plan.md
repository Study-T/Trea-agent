# Test Plan Template
# 测试计划模板

## Test Plan Info / 测试计划信息
- **Project / 项目**: [Name]
- **Requirement ID / 需求编号**: REQ-YYYY-NNN
- **Version / 版本**: [Version]
- **Author / 作者**: [Name]
- **Date / 日期**: YYYY-MM-DD
- **Environment / 环境**: [BOE / PPE / PROD]

## Test Scope / 测试范围

### In Scope / 测试范围内
- [Feature 1]
- [Feature 2]

### Out of Scope / 测试范围外
- [Item 1]

## Test Strategy / 测试策略

| Test Type | Priority | Coverage Target | Tools |
|-----------|----------|-----------------|-------|
| Functional | High | 100% core flows | Manual |
| Fund Safety | Critical | 100% amount precision | Manual + Script |
| Performance | Medium | P99 < 500ms | Load Test Tool |
| Security | High | OWASP Top 10 | Scanner |
| Compatibility | Medium | Top 5 devices | Device Lab |
| i18n | Medium | All supported locales | Manual |

## Test Cases / 测试用例

| TC# | Category | Description | Precondition | Steps | Expected Result | Priority |
|-----|----------|-------------|--------------|-------|-----------------|----------|
| TC-001 | [Category] | [Description] | [Precondition] | 1. Step 1 2. Step 2 | [Expected] | [P0/P1/P2] |

## Test Data / 测试数据
| Data Type | Source | Description |
|-----------|--------|-------------|
| [Type] | [Source] | [Description] |

## Risk Assessment / 风险评估
| Risk | Impact | Mitigation |
|------|--------|------------|
| [Risk] | [High/Med/Low] | [Mitigation] |

## Entry Criteria / 进入条件
- [ ] Tech design reviewed and approved
- [ ] Code merged to test branch
- [ ] Test environment ready
- [ ] Test data prepared

## Exit Criteria / 退出条件
- [ ] All P0/P1 test cases passed
- [ ] No critical/high bugs open
- [ ] Performance meets SLA
- [ ] Test report delivered

## Schedule / 排期
| Phase | Start | End | Owner |
|-------|-------|-----|-------|
| Test Preparation | YYYY-MM-DD | YYYY-MM-DD | [Name] |
| Functional Testing | YYYY-MM-DD | YYYY-MM-DD | [Name] |
| Specialized Testing | YYYY-MM-DD | YYYY-MM-DD | [Name] |
| Regression Testing | YYYY-MM-DD | YYYY-MM-DD | [Name] |
| Test Report | YYYY-MM-DD | YYYY-MM-DD | [Name] |
