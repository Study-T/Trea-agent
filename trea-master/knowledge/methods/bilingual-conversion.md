# Bilingual Documentation Conversion Method
# 双语文档转换方法

## Context
## 背景

When converting documentation to bilingual format (English + Chinese, two lines each), special care must be taken with certain patterns to avoid breaking the document structure.
将文档转换为双语格式（英文+中文，每种语言一行）时，必须特别注意某些模式，以避免破坏文档结构。

## Problem
## 问题

Using simple ` / ` split patterns can break:
简单的 ` / ` 分割模式可能破坏：

- **Angle brackets** `< >`: `<text / text>` splits into broken `<text` and `text>`
- **尖括号**: 同上
- **Parentheses** `( )`: `Text (Chinese)` splits incorrectly
- **括号**: 同上
- **Table formatting**: `Chinese / English` should be `English / Chinese` for consistency
- **表格格式**: 同上

## Solution
## 解决方案

### Step 1: Initial Conversion
### 步骤1: 初始转换

Use automated script to split `English / Chinese` into two lines:
使用自动化脚本将 `English / Chinese` 拆分为两行：

```python
# Split pattern on " / " (space-slash-space)
# 在 " / " (空格-斜杠-空格) 上拆分
```

### Step 2: Verify and Fix
### 步骤2: 验证和修复

Run these grep patterns to find issues:
运行以下grep模式查找问题：

```bash
# Find residual / patterns
grep -rn " / " .
# 查找残留的 / 模式

# Find broken angle brackets
grep -rn "<[^>]*$" .
grep -rn "^[^>]*>" .
# 查找破损的尖括号

# Find wrong order (Chinese before English on same line)
grep -rn "^[^/]*中文.*英文" .
# 查找错误顺序（中文在英文前）
```

### Step 3: Manual Fix
### 步骤3: 手动修复

Fix each issue file by file:
逐个文件修复每个问题：

- For angle brackets: Keep only Chinese content inside `< >`
- 对于尖括号: 只保留尖括号内的中文内容
- For execution order blocks: Ensure English line is first, Chinese second
- 对于执行顺序块: 确保英文行在前，中文行在后
- For tables: Use `English / 中文` format
- 对于表格: 使用 `English / 中文` 格式

## Key Files
## 关键文件

- `.trae/skills/workflow-engine/pm/leader.md`
- `.trae/skills/workflow-engine/rd/leader.md`
- `.trae/skills/workflow-engine/qa/leader.md`
- All 37 specialist `instructions.md` files

## Tags
## 标签

#documentation #bilingual #formatting #workflow-engine
