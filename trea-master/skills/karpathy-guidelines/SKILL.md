---
name: "karpathy-guidelines"
description: "Behavioral guidelines to reduce common LLM coding mistakes, derived from Andrej Karpathy's observations on LLM coding pitfalls."
---

# Karpathy Guidelines
# Karpathy 编程准则

## Overview
## 概览

These are behavioral guidelines to reduce common LLM coding mistakes, derived from Andrej Karpathy's observations on LLM coding pitfalls.
这些是行为准则，用于减少常见的 LLM 编程错误，源自 Andrej Karpathy 对 LLM 编程陷阱的观察。

**Tradeoff / 权衡**: These guidelines bias toward caution over speed. For trivial tasks, use judgment.
这些准则偏向谨慎而非速度。对于简单任务要自行判断。

---

## 1. Think Before Coding
## 1. 编码前先思考

**Principle / 原则**: Don't assume. Don't hide confusion. Surface tradeoffs.
不要假设。不要隐藏困惑。要暴露权衡。

### Before implementing / 实施前：
- State your assumptions explicitly / 明确陈述你的假设
- If uncertain, ask / 如果不确定，要问
- Present multiple interpretations rather than choosing silently / 提出多种解释而不是沉默选择
- Suggest simpler approaches and push back when appropriate / 适当建议更简单的方法并 push back
- Stop and name confusion rather than proceeding blindly / 停下来说出困惑而不是盲目继续

---

## 2. Simplicity First
## 2. 简单性优先

**Principle / 原则**: Minimum code that solves the problem. Nothing speculative.
解决问题的最少代码。不做投机性代码。

### Practical guidance / 实践指导：

- No abstractions for single-use code / 不要为一次性使用的代码创建抽象
- No "flexibility" or "configurability" that wasn't requested / 不要添加没有要求的"灵活性"或"可配置性"
- No error handling for impossible scenarios / 不要处理不可能的场景的错误处理
- No features beyond what was asked / 不要添加超出需求的功能
- If you write 200 lines and it could be 50, rewrite it / 如果你写了200行而本来可以50行，那就重写

### Ask yourself / 问问自己：
> "Would a senior engineer say this is overcomplicated?"
> "高级工程师会说这太复杂了吗？"

If yes, simplify. / 如果是，那就简化。

---

## 3. Surgical Changes
## 3. 精准修改

**Principle / 原则**: Touch only what you need to touch.
只修改你需要修改的地方。

### Practical guidance / 实践指导：

- When changing existing code, make the smallest possible change / 修改现有代码时，做尽可能最小的修改
- Don't rewrite entire files unless necessary / 除非必要，不要重写整个文件
- Be precise about what you're modifying / 对于你要修改的内容要精确
- Avoid cascading changes that affect unrelated code / 避免影响无关代码的连锁修改

---

## 4. Goal-Driven
## 4. 目标驱动

**Principle / 原则**: Always know what you're working toward.
始终知道你在为什么而努力。

### Before starting / 开始前：
- Verify you understand the user's goal / 验证你理解用户的目标
- Confirm the acceptance criteria / 确认验收标准
- Know what "done" looks like / 知道"完成"是什么样的

### During work / 工作期间：
- Check your progress against the goal / 对照目标检查进度
- When blocked, identify what's blocking you / 遇到阻碍时，找出是什么阻碍了你
- Communicate blockers clearly / 清楚地沟通阻碍

---

## Summary
## 总结

| Principle | Key Action |
|-----------|------------|
| Think First | Don't assume, ask if uncertain / 不要假设，不确定就问 |
| Simplicity | Minimum code, no speculation / 最少代码，不投机 |
| Surgical | Touch only what you need / 只修改需要的 |
| Goal-Driven | Always know the target / 始终知道目标 |

---

## Examples
## 示例

See `EXAMPLES.md` for real-world code examples demonstrating these principles.
有关展示这些原则的实际代码示例，请参阅 `EXAMPLES.md`。

### Example 1: Hidden Assumptions / 示例1：隐藏的假设

**User Request / 用户请求**: "Add a feature to export user data"
**用户请求**: "添加导出用户数据的功能"

❌ **What LLMs Do (Wrong) / LLM常做的（错误）**:
```python
def export_users(format='json'):
    """Export all users"""
    ...
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Clarifying first / 先澄清
- What format? (JSON, CSV, XML?)
- All users or filtered?
- What fields to include?
# 什么格式？全部用户还是筛选？包含哪些字段？
```

### Example 2: Over-abstraction / 示例2：过度抽象

❌ **What LLMs Do (Wrong) / LLM常做的（错误）**:
```python
class BaseExporter:
    def __init__(self, config):
        ...
    def validate(self):
        ...

class JSONExporter(BaseExporter):
    ...

class CSVExporter(BaseExporter):
    ...
```

✅ **What to Do Instead / 应该怎么做**:
```python
# Just write what you need / 只写你需要的
def export_users_json():
    """Export users to JSON"""
    ...
```
