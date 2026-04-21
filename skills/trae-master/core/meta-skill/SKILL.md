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
| context-log | core/context-log | Automatic context summary recording (triggered after user confirmation) |
| boss | skills/boss | Boss智能体，由当前AI担任，审核+阶段切换+数据请求中转 |
| workflow-engine | skills/workflow-engine | PM→RD→QA workflow |
| pm-leader | skills/pm-leader | PM组长智能体，动态调度PM专员 |
| rd-leader | skills/rd-leader | RD组长智能体，代码优先+动态调度RD专员 |
| qa-leader | skills/qa-leader | QA组长智能体，动态调度QA专员 |
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
→ Check `core/meta-skill/REGISTRY.md`
→ If `skills/project-manager` status is `Placeholder`, use `skills/workflow-engine` PM phase instead
→ Only if registry status is `Active`, use `skills/project-manager`

User wants help with coding/development?
→ Check `core/meta-skill/REGISTRY.md`
→ If `skills/developer` status is `Placeholder`, use `skills/workflow-engine` RD phase instead
→ Only if registry status is `Active`, use `skills/developer`

User wants help with testing?
→ Check `core/meta-skill/REGISTRY.md`
→ If `skills/qa-tester` status is `Placeholder`, use `skills/workflow-engine` QA phase instead
→ Only if registry status is `Active`, use `skills/qa-tester`

User wants to know about existing skills?
→ This meta-skill (show registry)
```

**Important**: Do not dispatch Placeholder skills for real work. Always check `core/meta-skill/REGISTRY.md` first.
**重要**：不要把 Placeholder 技能用于真实工作。必须先检查 `core/meta-skill/REGISTRY.md`。

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
