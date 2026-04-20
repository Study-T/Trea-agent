---
name: "workflow-engine"
description: "PM→RD→QA sequential workflow engine. Invoke when user wants to run a real project workflow."
---

# Workflow Engine
# 工作流引擎

## Purpose
## 用途

Execute the complete PM → RD → QA workflow. This is a real workflow engine, not a simulator.
执行完整的 PM → RD → QA 工作流。这是一个真正的工作流引擎，不是模拟器。

## When to Use
## 何时使用

When the user provides a project requirement that needs:
当用户提供需要以下内容的项目需求时：

- Requirement analysis / 需求分析
- Technical design / 技术设计
- Testing / 测试

## Recording Rules
## 记录规则

**IMPORTANT: Record to context-log ONLY after user confirms**
**重要：只有在用户确认后才记录到 context-log**

```
PM completes → PM Leader approves → Boss approves → User confirms "OK" → Record to context-log
RD completes → RD Leader approves → Boss approves → User confirms "OK" → Record to context-log
QA completes → QA Leader approves → Boss approves → User confirms "OK" → Record to context-log
```

## How It Works
## 如何工作

### Phase 1: PM
PM Leader assigns 11 specialists in order:
PM 组长按顺序分配11个专员：

1. Requirement Understanding / 需求理解
2. User Research / 用户调研
3. Data Analyst / 数据分析
4. Market Research / 市场调研
5. Compliance & Risk / 合规风控
6. Internationalization / 国际化
7. Data Tracking / 数据埋点
8. External Partner / 外部合作
9. Value Assessment / 价值评估
10. Doc Writer / 文档编写
11. Requirement Review / 需求审查

### Phase 2: RD
RD Leader assigns 13 specialists in order:
RD 组长按顺序分配13个专员：

1. Tech Requirement / 技术需求
2. Business Logic / 业务逻辑
3. Project Query / 项目查询
4. API Doc / API文档
5. Tech Design / 技术设计
6. Database Design / 数据库设计
7. Data Flow / 数据流设计
8. Coding Standards / 编码规范
9. Dependency / 依赖管理
10. Coding Impl / 编码实现
11. Integration / 接口联调
12. Quality Assurance / 质量保障
13. Delivery & Ops / 交付运维

### Phase 3: QA
QA Leader assigns 13 specialists in order:
QA 组长按顺序分配13个专员：

1. Test Requirement / 测试需求
2. Test Case / 测试用例
3. Test Preparation / 测试准备
4. Functional Test / 功能测试
5. Fund Safety / 资金安全
6. Verification Test / 验证测试
7. Performance Test / 性能测试
8. Security Test / 安全测试
9. Compatibility & i18n / 兼容性国际化
10. Gray Test / 灰度测试
11. Auto Test / 自动化测试
12. Bug Recorder / 缺陷记录
13. Test Delivery / 测试交付

## Context Recording
## 上下文记录

All phase completions are recorded to `context-log/logs/YYYY-MM-DD.md`
所有阶段完成都会记录到 `context-log/logs/YYYY-MM-DD.md`

See `core/context-log/SKILL.md` for recording format.
记录格式请参阅 `core/context-log/SKILL.md`。

## Directory Structure
## 目录结构

```
workflow-engine/
├── SKILL.md
├── boss/
│   └── instructions.md
├── pm/
│   ├── leader.md
│   └── specialists/
│       └── [11 specialists]
├── rd/
│   ├── leader.md
│   └── specialists/
│       └── [13 specialists]
├── qa/
│   ├── leader.md
│   └── specialists/
│       └── [13 specialists]
├── shared/
│   └── [templates and formats]
└── requirements/
    ├── templates/
    └── active/
```
