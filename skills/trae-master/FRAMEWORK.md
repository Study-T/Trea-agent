---
name: "trae-master"
description: "Trae Master - R&D Workflow Framework (Boss-PM-RD-QA)."
---

# Trae Master
# Trae Master 框架

## Overview
## 概览

This is a modular framework for developing, organizing, and executing skills.
这是一个模块化框架，用于开发、组织和执行技能。

## Four-Layer Architecture
## 四层架构

```
Layer 1: 认知层 (Cognition)
Layer 2: 规则层 (Rules)
Layer 3: 执行层 (Execution)
Layer 4: 上下文层 (Context)
```

### Layer 1: Cognition
### 认知层

Self-awareness: What am I and what can I do?
自我认知：我是什么，我能做什么？

```
core/meta-skill/IDENTITY.md - 框架身份声明
core/meta-skill/SKILL.md - 框架自我认知
core/meta-skill/EVOLUTION.md - 自我进化机制
core/meta-skill/EVOLUTION_RULES.md - 进化规则
core/meta-skill/EVOLUTION_LOG.md - 进化历史
```

### Layer 2: Rules
### 规则层

Protocols and rules: How do things work?
规则协议：事情如何运作？

```
core/PROTOCOL.md - 技能通信协议
core/dispatch-rules.md - 调度与通信规则
core/acceptance-criteria.md - 交付验收标准
```

### Layer 3: Execution
### 执行层

Skills and workflow: How to get things done?
技能执行：如何完成工作？

```
skills/
├── workflow-engine/ - 工作流引擎 (PM→RD→QA)
├── project-manager/ - 项目管理
├── developer/ - 开发
├── qa-tester/ - 测试
└── karpathy-guidelines/ - 编码规范
```

### Layer 4: Context
### 上下文层

Context and knowledge: What has been done?
上下文与知识：已经完成了什么？

```
core/context-log/ - 每日工作日志
knowledge/
├── methods/ - 方法库
└── templates/ - 模板库
```

## Architecture Tree
## 架构树

```
trae-master/
├── FRAMEWORK.md                    ← This file / 本文件
│
├── Layer 1: 认知层
│   └── core/meta-skill/            ← Self-awareness + Evolution / 自我认知+进化
│       ├── IDENTITY.md             ← Framework identity / 框架身份
│       ├── SKILL.md
│       ├── REGISTRY.md
│       ├── EVOLUTION.md            ← Self-evolution / 自我进化
│       ├── EVOLUTION_RULES.md      ← Evolution rules / 进化规则
│       └── EVOLUTION_LOG.md       ← Evolution history / 进化历史
│
├── Layer 2: 规则层
│   ├── core/PROTOCOL.md            ← Communication protocol / 通信协议
│   ├── core/dispatch-rules.md      ← Dispatch rules / 调度规则
│   └── core/acceptance-criteria.md ← Acceptance criteria / 验收标准
│
├── Layer 3: 执行层
│   └── skills/                     ← Skills layer / 技能层
│       ├── workflow-engine/        ← PM→RD→QA workflow / 工作流引擎
│       ├── project-manager/        ← Project management / 项目管理
│       ├── developer/              ← Development / 开发
│       ├── qa-tester/              ← Testing / 测试
│       └── karpathy-guidelines/    ← Coding standards / 编码规范
│
└── Layer 4: 上下文层
    ├── core/context-log/            ← Daily logs / 每日日志
    │   ├── SKILL.md
    │   └── logs/
    │       └── YYYY-MM-DD.md
    └── knowledge/                   ← Knowledge base / 知识库
        ├── bnpl-domain/             ← BNPL domain knowledge / BNPL领域知识库（需用户自行创建）
        │   └── SKILL.md             ← 28 sections, bilingual / 28章节双语
        ├── methods/
        └── templates/
```

## Role Hierarchy
## 角色层级

```
Boss (老板)
└── 调度 → PM组长 / RD组长 / QA组长
          └── 调度 → 各组专员
```

| 角色 | 可调度 | 可通信 |
|-----|-------|-------|
| Boss | 只能调度组长 | 组长 + 用户（仅限需求接收和数据请求） |
| 组长 | 调度组内专员 | 和Boss + 同组专员 |
| 专员 | 不能调度 | 只能和同组专员 |

## Core Principles
## 核心原则

1. **Modularity / 模块化** - Each skill is self-contained and independent
2. **Reusability / 可复用性** - Skills can be reused across different contexts
3. **Standardization / 标准化** - All skills follow the same interface standards
4. **User Confirmation / 用户确认** - Actions are recorded only after user confirms
5. **Data Authenticity / 数据真实性** - Strictly prohibit speculating, judging, inferring, or predicting any false information. All data must be real and verifiable. When data is missing, must explicitly report and wait for real data, never fabricate or guess
   严禁根据任何东西推测、判断、推断、预测等虚假信息，所有的数据必须是真实的、可验证的。当数据缺失时，必须明确上报并等待真实数据，严禁编造或猜测

## Framework Execution Checklist
## 框架执行校验清单

**使用框架时，必须在每个关键节点校验以下规则是否被遵守。未通过校验则禁止继续执行。**

### 启动前校验（Pre-flight Check）

使用框架前必须完成：

- [ ] 已读取 FRAMEWORK.md
- [ ] 已读取 core/PROTOCOL.md
- [ ] 已读取 core/dispatch-rules.md
- [ ] 已读取 core/acceptance-criteria.md
- [ ] 已读取 core/meta-skill/IDENTITY.md
- [ ] 已读取 core/meta-skill/SKILL.md
- [ ] 已读取 core/meta-skill/REGISTRY.md
- [ ] 已读取 core/meta-skill/EVOLUTION.md
- [ ] 已读取 core/meta-skill/EVOLUTION_RULES.md
- [ ] 已读取 core/meta-skill/EVOLUTION_LOG.md
- [ ] 已读取 core/context-log/SKILL.md
- [ ] 已读取 skills/karpathy-guidelines/SKILL.md
- [ ] 已读取 skills/workflow-engine/SKILL.md
- [ ] 已读取 skills/workflow-engine/boss/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/leader.md
- [ ] 已读取 skills/workflow-engine/rd/leader.md
- [ ] 已读取 skills/workflow-engine/qa/leader.md
- [ ] 已读取 skills/workflow-engine/requirements/RECORDER_PROTOCOL.md
- [ ] 已读取 skills/workflow-engine/shared/output-format.md
- [ ] 已读取 skills/workflow-engine/shared/review-template.md
- [ ] 已读取 skills/workflow-engine/shared/error-package.md
- [ ] 已读取 skills/workflow-engine/shared/data-request-template.md
- [ ] 已读取 skills/project-manager/SKILL.md
- [ ] 已读取 skills/developer/SKILL.md
- [ ] 已读取 skills/qa-tester/SKILL.md
- [ ] 已读取 knowledge/bnpl-domain/SKILL.md
- [ ] 已读取 knowledge/methods/SKILL.md
- [ ] 已读取 SKILL.md
- [ ] 已读取 skills/workflow-engine/requirements/INDEX.md
- [ ] 已读取 knowledge/methods/karpathy-guidelines-examples.md
- [ ] 已读取 knowledge/templates/SKILL.md
- [ ] 已读取 DOCUMENTATION.md
- [ ] 已读取 README.md
- [ ] 已读取 knowledge/methods/README.md
- [ ] 已读取 knowledge/methods/bilingual-conversion.md
- [ ] 已读取 knowledge/templates/README.md
- [ ] 已读取 knowledge/templates/code-review.md
- [ ] 已读取 knowledge/templates/meeting-notes.md
- [ ] 已读取 knowledge/templates/project-plan.md
- [ ] 已读取 knowledge/templates/status-report.md
- [ ] 已读取 knowledge/templates/test-plan.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/01-requirement-understanding/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/02-data-analyst/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/03-market-research/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/04-user-research/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/05-compliance-risk/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/06-internationalization/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/07-data-tracking/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/08-external-partner/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/09-value-assessment/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/10-doc-writer/instructions.md
- [ ] 已读取 skills/workflow-engine/pm/specialists/11-requirement-review/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/01-test-requirement/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/02-test-case/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/03-test-preparation/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/04-functional-test/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/05-fund-safety/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/06-verification-test/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/07-performance-test/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/08-security-test/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/09-compatibility-test/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/10-gray-test/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/11-auto-test/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/12-bug-recorder/instructions.md
- [ ] 已读取 skills/workflow-engine/qa/specialists/13-test-delivery/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/01-tech-requirement/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/02-business-logic/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/03-project-query/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/04-api-doc/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/05-tech-design/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/06-database-design/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/07-data-flow/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/08-coding-standards/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/09-coding-impl/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/10-integration/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/11-quality-assurance/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/12-delivery-ops/instructions.md
- [ ] 已读取 skills/workflow-engine/rd/specialists/13-dependency/instructions.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-index.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-metadata.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-pm-record.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-prd.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-qa-record.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-rd-record.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-summary.md
- [ ] 已读取 skills/workflow-engine/requirements/templates/TEMPLATE-timeline.md
- [ ] 已读取 skills/workflow-engine/shared/README.md
- [ ] 已读取 skills/pm-leader/SKILL.md
- [ ] 已读取 skills/rd-leader/SKILL.md
- [ ] 已读取 skills/qa-leader/SKILL.md
- [ ] 已读取 skills/boss/SKILL.md

### PM阶段校验

| 校验项 | 规则来源 | 不通过处理 |
|--------|---------|-----------|
| 所有专员产出数据有明确来源 | acceptance-criteria.md 数据真实性验证 | 打回，要求标注来源 |
| 无未标注的推断/推测/预测内容 | acceptance-criteria.md Boss审核数据真实性校验 | 打回，要求删除或标注DATA_MISSING |
| 缺失数据已标注DATA_MISSING | acceptance-criteria.md DATA_MISSING标注 | 打回，要求补标 |
| 关键数据与PRD原文一致 | acceptance-criteria.md 文档原文对照 | 打回，要求修正 |

### Boss审核校验

| 校验项 | 规则来源 | 不通过处理 |
|--------|---------|-----------|
| 执行Boss审核数据真实性校验检查清单 | acceptance-criteria.md Boss审核检查清单 | 审核无效，重新审核 |
| 数据来源追溯 | acceptance-criteria.md 数据来源追溯 | 打回 |
| 推断内容检测 | acceptance-criteria.md 推断内容检测 | 打回 |

### 阶段切换校验

| 校验项 | 规则来源 | 不通过处理 |
|--------|---------|-----------|
| 上一阶段Boss审核通过 | PROTOCOL.md 阶段切换前置条件 | 禁止切换 |
| 上一阶段用户确认 | PROTOCOL.md 阶段切换前置条件 | 禁止切换 |
| 上一阶段日志已记录 | PROTOCOL.md 阶段切换前置条件 | 禁止切换，先记录日志 |

### RD阶段校验

| 校验项 | 规则来源 | 不通过处理 |
|--------|---------|-----------|
| Round 1已查代码（项目结构/接口/IDL） | dispatch-rules.md RD代码优先规则 | 打回，先查代码 |
| 技术方案基于代码查询结果 | dispatch-rules.md RD代码优先规则 | 打回，重新设计 |

### 任务完成后校验

| 校验项 | 规则来源 | 不通过处理 |
|--------|---------|-----------|
| 所有阶段日志已记录 | PROTOCOL.md 阶段切换规则 | 补录后再继续 |
| 执行进化分析检查清单 | EVOLUTION.md 进化分析检查清单 | 必须执行 |
| 有问题才进化，没问题不进化 | EVOLUTION.md 核心原则 | 无问题则跳过进化 |

## Recording Flow
## 记录流程

```
Phase completes → Leader reviews and approves → Boss reviews and approves → Show to user → User confirms "OK" → ★ Auto-record to context-log → Verify log recorded ✅ → Enter next phase
```

## Self-Evolution Flow
## 自我进化流程

```
用户整体任务完成
        ↓
日志总结：回顾整个任务过程，记录到context-log
        ↓
进化分析：逐项检查进化分析检查清单
        ↓
    有问题 → 生成进化提案 → 展示给用户 → 用户决定
    没有问题 → 不进行进化 → 任务结束
```

## How to Use
## 如何使用

1. **MUST complete Pre-flight Check first / 必须先完成启动前校验**: Execute the Pre-flight Check in this FRAMEWORK.md (read ALL 91 framework files before using the framework)
2. **必须先完成启动前校验**: 执行本 FRAMEWORK.md 中的启动前校验（使用框架前必须读取全部91个框架文件）
3. Choose a skill from Layer 3 (Execution)
4. 从第三层（执行层）选择技能
5. Read that skill's SKILL.md and invoke it
6. 阅读该技能的 SKILL.md 并调用它
7. **Follow the Framework Execution Checklist at every checkpoint**
8. **在每个校验节点遵循框架执行校验清单**
