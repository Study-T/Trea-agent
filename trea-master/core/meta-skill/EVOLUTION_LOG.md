# Evolution Log
# 进化日志

## Purpose
## 目的

Record all framework evolution history.
记录框架所有进化历史。

## Format
## 格式

```markdown
## YYYY-MM-DD - [Evolution Title]
## 日期 - 进化标题

- **Trigger**: [What triggered this evolution]
- **触发**: [什么触发了这次进化]
- **Proposal**: [Brief proposal summary]
- **提案**: [提案摘要]
- **Decision**: [Approved/Rejected]
- **决定**: [批准/拒绝]
- **Executed**: [What was changed]
- **执行**: [具体变更内容]
- **Date**: YYYY-MM-DD
- **日期**: YYYY-MM-DD
```

## Log Entries
## 日志条目

<!-- Add new entries below this line -->
<!-- 在此行下方添加新条目 -->

---

## 2026-04-20 - Boss审核数据真实性校验强化
## 2026-04-20 - Boss Review Data Authenticity Verification Enhancement

- **Trigger**: PM阶段第1次产出包含推断的4种用户状态，Boss审核未拦截直接通过，后经用户指出才打回
- **触发**: PM阶段产出包含推断内容，Boss审核未拦截
- **Proposal**: 在Boss审核标准中增加数据真实性校验环节，Boss审核必须验证每个专员产出的数据来源
- **提案**: Boss审核增加数据来源追溯、推断内容检测、DATA_MISSING标注、文档原文对照4项校验
- **Decision**: Approved (自动进化)
- **决定**: 批准（自动进化）
- **Executed**: 修改 `core/acceptance-criteria.md`，新增"Boss Review Data Authenticity Verification"章节，包含4项校验标准和Boss审核检查清单
- **执行**: acceptance-criteria.md 新增 Boss审核数据真实性校验表 + 检查清单
- **Date**: 2026-04-20
- **日期**: 2026-04-20

## 2026-04-20 - 阶段切换自动记录日志规则
## 2026-04-20 - Phase Transition Auto-Logging Rule

- **Trigger**: PM阶段用户确认后，AI直接进入RD阶段，未记录PM阶段日志
- **触发**: 用户确认后未自动记录日志，直接进入下一阶段
- **Proposal**: 在阶段切换规则中增加日志记录前置条件，进入下一阶段前必须校验上一阶段日志已记录
- **提案**: 阶段切换前置条件增加"日志已记录"校验，未记录则禁止进入下一阶段
- **Decision**: Approved (自动进化)
- **决定**: 批准（自动进化）
- **Executed**: 修改 `core/PROTOCOL.md`，新增"Phase Transition Rules"章节，定义4项前置条件和阶段切换流程
- **执行**: PROTOCOL.md 新增阶段切换规则：Boss审核→用户确认→★自动记录日志→校验→进入下一阶段
- **Date**: 2026-04-20
- **日期**: 2026-04-20

## 2026-04-20 - RD阶段代码优先规则
## 2026-04-20 - RD Phase Code-First Rule

- **Trigger**: RD阶段先凭空设计技术方案，后经用户要求才查实际代码，发现架构已存在
- **触发**: RD阶段未查代码就设计技术方案，导致方案脱离实际
- **Proposal**: RD阶段Round 1必须先查代码（项目结构/接口定义/现有实现/IDL），Round 2再基于代码查询结果设计方案
- **提案**: RD阶段强制代码优先，Round 1查代码，Round 2设计方案，未查代码就设计方案Boss必须打回
- **Decision**: Approved (自动进化)
- **决定**: 批准（自动进化）
- **Executed**: 修改 `core/dispatch-rules.md`，新增"RD Phase Code-First Rule"章节，定义Round 1/2调度顺序
- **执行**: dispatch-rules.md 新增RD代码优先规则：Round 1必须查代码→Round 2基于代码设计方案
- **Date**: 2026-04-20
- **日期**: 2026-04-20

---

## 2026-04-19 - Initial Framework Setup
## 2026-04-19 - 框架初始搭建

- **Trigger**: Framework created with four-layer architecture
- **触发**: 框架创建，采用四层架构
- **Proposal**: Create trae-skills-framework with Cognition/Rules/Execution/Context layers
- **提案**: 创建四层架构框架
- **Decision**: Approved
- **决定**: 批准
- **Executed**: Created FRAMEWORK.md, core/dispatch-rules.md, core/acceptance-criteria.md, EVOLUTION.md, EVOLUTION_RULES.md
- **执行**: 创建了框架核心文件
- **Date**: 2026-04-19
- **日期**: 2026-04-19

## Pending Tracking
## 待处理追踪

<!-- Track recurring issues here before creating proposals -->
<!-- 在创建提案前，在此追踪反复出现的问题 -->
