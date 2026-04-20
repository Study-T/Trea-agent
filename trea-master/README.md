# Trae Skills Framework Guide
# Trae Skills 框架使用指南

## What is This Framework?
## 这是什么框架？

This framework provides a standardized way to organize and execute skills. Think of it as an "operating system" for skills.
这个框架提供了一种标准化的方式来组织和执行技能。可以把它想象成技能的"操作系统"。

## Four-Layer Architecture
## 四层架构

```
Layer 1: 认知层 (Cognition) - Who am I and what can I do?
Layer 2: 规则层 (Rules)     - How do things work?
Layer 3: 执行层 (Execution)  - How to get things done?
Layer 4: 上下文层 (Context)  - What has been done?
```

### Layer 1: Cognition
### 认知层

Self-awareness and self-evolution.
自我认知与自我进化。

- **IDENTITY.md**: Framework identity declaration
- **IDENTITY.md**: 框架身份声明
- **EVOLUTION.md**: Self-evolution mechanism
- **EVOLUTION.md**: 自我进化机制
- **EVOLUTION_RULES.md**: Evolution trigger rules
- **EVOLUTION_RULES.md**: 进化触发规则
- **EVOLUTION_LOG.md**: Evolution history
- **EVOLUTION_LOG.md**: 进化历史

### Layer 2: Rules
### 规则层

Protocols, dispatch rules, and acceptance criteria.
协议、调度规则和验收标准。

- **PROTOCOL.md**: Skill communication protocol (all cross-phase handoffs via Boss)
- **PROTOCOL.md**: 技能通信协议（所有跨阶段交接通过Boss中转）
- **dispatch-rules.md**: Dispatch and communication rules
- **dispatch-rules.md**: 调度与通信规则
- **acceptance-criteria.md**: Acceptance criteria
- **acceptance-criteria.md**: 验收标准

### Layer 3: Execution
### 执行层

Skills and workflow engine.
技能和工作流引擎。

- **workflow-engine**: Complete PM→RD→QA workflow
- **workflow-engine**: 完整的 PM→RD→QA 工作流
- **project-manager**: Project management capabilities
- **project-manager**: 项目管理能力
- **developer**: Development capabilities
- **developer**: 开发能力
- **qa-tester**: Testing capabilities
- **qa-tester**: 测试能力

### Layer 4: Context
### 上下文层

Daily logs and knowledge base.
每日日志和知识库。

- **context-log**: Automatic context recording (one file per day)
- **context-log**: 自动上下文记录（每天一个文件）
- **knowledge/methods**: Reusable problem-solving methods
- **knowledge/methods**: 可复用的问题解决方法
- **knowledge/templates**: Standardized templates
- **knowledge/templates**: 标准化模板

## Quick Start
## 快速开始

1. Read `FRAMEWORK.md` to understand the overall structure
2. 阅读 `FRAMEWORK.md` 了解整体结构
3. Read `core/meta-skill/IDENTITY.md` to understand framework identity
4. 阅读 `core/meta-skill/IDENTITY.md` 了解框架身份
5. Read `core/dispatch-rules.md` to understand dispatch and communication
6. 阅读 `core/dispatch-rules.md` 了解调度与通信规则
7. Choose the skill you need from Layer 3 (Execution)
8. 从第三层（执行层）选择你需要的技能
9. Read that skill's `SKILL.md`
10. 阅读该技能的 `SKILL.md`
11. Invoke it by describing your requirement
12. 通过描述你的需求来调用它

## Recording Flow
## 记录流程

```
User input requirement
        ↓
   Execute workflow
        ↓
   Boss reviews and approves
        ↓
   Show output to user ← User confirms "OK"
        ↓
   Record to context-log/logs/YYYY-MM-DD.md
```

## Self-Evolution Flow
## 自我进化流程

```
AI discovers optimization opportunity
        ↓
AI generates Framework Optimization Proposal
        ↓
Show to user
        ↓
User approves → AI executes → Record to evolution log
User rejects → AI notes reason → Wait for next trigger
```

## Adding New Skills
## 添加新技能

1. Create your skill in `skills/[your-skill]/`
2. 在 `skills/[your-skill]/` 中创建你的技能
3. Create a `SKILL.md` file following the standard template
4. 按照标准模板创建 `SKILL.md` 文件
5. Register it in the `core/meta-skill/REGISTRY.md`
6. 在 `core/meta-skill/REGISTRY.md` 中注册它
