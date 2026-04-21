# Error Package Format
# 错误包格式

When a review is rejected, the error package must be attached. This is the standard format.
当审核被拒绝时，必须附带错误包。这是标准格式。

## Structure
## 结构

An error package contains:
错误包包含：
1. **Errors / 错误**: What specifically is wrong / 具体什么有问题
2. **Suggestions / 建议**: How to fix it / 如何修复
3. **Target / 目标**: Who needs to redo their work / 谁需要返工

## Format
## 格式

```json
{
  "reviewer": "<who rejected / 谁拒绝的>",
  "phase": "<PM/RD/QA>",
  "iteration": "<which attempt / 第几次尝试>",
  "errors": [
    "<specific error description 1 / 具体错误描述1>",
    "<specific error description 2 / 具体错误描述2>"
  ],
  "suggestions": [
    "<how to fix error 1 / 如何修复错误1>",
    "<how to fix error 2 / 如何修复错误2>"
  ],
  "target": "<who receives this: leader name or 'all specialists' / 谁接收：组长名称或'所有专员'>"
}
```

## Rules
## 规则

- Errors must be SPECIFIC — point to exact issues, not vague complaints / 错误必须具体——指向确切问题，而非模糊抱怨
- Suggestions must be ACTIONABLE — tell them what to change, not just "do better" / 建议必须可执行——告诉他们改什么，而非只说"做得更好"
- When a leader rejects, the target is "all specialists" in that group / 当组长拒绝时，目标是该组的"所有专员"
- When the boss rejects, the target is the leader, who then distributes to all specialists / 当Boss拒绝时，目标是组长，组长再分发给所有专员
- Specialists MUST reference the error package when redoing their work / 专员返工时必须参考错误包
