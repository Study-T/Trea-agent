---
name: "trae-skills-framework"
description: "Trae Skills Framework - A modular skill development and execution framework."
---

# Trae Skills Framework
# Trae Skills 框架

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
trae-skills-framework/
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

## Recording Flow
## 记录流程

```
Phase completes → Leader reviews and approves → Boss reviews and approves → Show to user → User confirms "OK" → Record to context-log
```

## Self-Evolution Flow
## 自我进化流程

```
AI使用框架工作
        ↓
AI发现需要优化的地方
        ↓
AI生成《框架优化建议提案》
        ↓
展示给用户
        ↓
用户同意 → AI执行修改
用户不同意 → AI重新分析
```

## How to Use
## 如何使用

1. Read this FRAMEWORK.md to understand the structure
2. 阅读本 FRAMEWORK.md 了解框架结构
3. Read core/meta-skill/SKILL.md to understand self-awareness
4. 阅读 core/meta-skill/SKILL.md 了解自我认知
5. Read core/dispatch-rules.md to understand dispatch and communication
6. 阅读 core/dispatch-rules.md 了解调度与通信规则
7. Choose a skill from Layer 3 (Execution)
8. 从第三层（执行层）选择技能
9. Read that skill's SKILL.md and invoke it
10. 阅读该技能的 SKILL.md 并调用它
