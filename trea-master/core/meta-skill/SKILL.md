---
name: "meta-skill"
description: "Skill registry and dispatcher. Helps understand available skills and how to invoke them."
---

# Meta Skill
# 元技能

## Purpose
## 用途

This is the skill registry and dispatcher. It helps understand what skills are available and how to create new ones.
这是技能注册表和调度器。它帮助了解有哪些可用的技能以及如何创建新技能。

## Registry
## 注册表

| Skill | Location | Description |
|-------|----------|-------------|
| context-log | core/context-log | Automatic context recording |
| workflow-engine | skills/workflow-engine | PM→RD→QA workflow |
| project-manager | skills/project-manager | Project management |
| developer | skills/developer | Software development |
| qa-tester | skills/qa-tester | QA testing |

## How to Use
## 如何使用

1. **Understand user intent**: What does the user want?
2. **理解用户意图**: 用户想要什么？
3. **Match to skill**: Find the best matching skill
4. **匹配技能**: 找到最匹配的技能
5. **Invoke skill**: Read that skill's SKILL.md and execute
6. **调用技能**: 阅读该技能的 SKILL.md 并执行
7. **Record context**: After user confirms, record to context-log
8. **记录上下文**: 用户确认后，记录到 context-log

## Skill Selection Logic
## 技能选择逻辑

```
User wants to run a project workflow?
→ skills/workflow-engine

User wants project planning/management?
→ skills/project-manager

User wants help with coding/development?
→ skills/developer

User wants help with testing?
→ skills/qa-tester

User wants to know about existing skills?
→ This meta-skill (show registry)
```

## How to Create a New Skill
## 如何创建新技能

### Step 1: Create Directory
### 步骤1：创建目录

Create `skills/[your-skill]/`
创建 `skills/[your-skill]/`

### Step 2: Create SKILL.md
### 步骤2：创建 SKILL.md

```markdown
---
name: "[your-skill]"
description: "What this skill does."
---

# Your Skill Name
# 你的技能名称

## Purpose
## 用途
Describe what this skill does.

## When to Use
## 何时使用
Describe when to invoke this skill.

## How It Works
## 如何工作
Describe the workflow/steps.
```

### Step 3: Register
### 步骤3：注册

Add to this file's registry section.
添加到本文件的注册表部分。
