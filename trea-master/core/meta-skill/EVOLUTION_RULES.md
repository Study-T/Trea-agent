# Evolution Rules
# 进化规则

## Trigger Conditions
## 触发条件

AI should propose optimization when:

1. **Repetitive patterns detected**
   发现重复出现的问题模式

2. **Missing capability discovered**
   发现框架缺少某个能力

3. **Rule inefficiency noticed**
   发现某个规则效率低下

4. **User complaint pattern**
   用户反复提出类似建议

5. **New skill requirement**
   多次需要某个skill但框架没有

## When to Propose
## 何时提议

| Situation | Action |
|-----------|--------|
| Minor issue | Note and continue working |
| 小问题 | 记录并继续工作 |
| Recurring issue | Create proposal after 3rd occurrence |
| 反复出现的问题 | 第3次出现后创建提案 |
| Major gap | Create proposal immediately |
| 重大缺失 | 立即创建提案 |

## Recurring Issue Tracking
## 反复问题追踪

For recurring issues, track occurrences before creating a proposal:
对于反复出现的问题，在创建提案前需要追踪出现次数：

Record each occurrence in `EVOLUTION_LOG.md` tracking section:
在 `EVOLUTION_LOG.md` 追踪区域记录每次出现：

```markdown
## Pending Tracking / 待处理追踪

### [Issue Description / 问题描述]
- **1st occurrence**: YYYY-MM-DD - [context]
- **2nd occurrence**: YYYY-MM-DD - [context]
- **3rd occurrence**: YYYY-MM-DD - [context] → **Create proposal / 创建提案**
```

When the 3rd occurrence is reached, create a formal proposal.
当第3次出现时，创建正式提案。

After proposal is created (approved or rejected), remove from tracking section.
提案创建后（无论批准或拒绝），从追踪区域移除。

## Proposal Rules
## 提案规则

1. **One proposal at a time**
   一次只提一个提案

2. **Clear problem statement**
   问题描述清晰

3. **Specific solution**
   解决方案具体

4. **Impact assessment included**
   包含影响评估

5. **User-friendly presentation**
   用户友好的呈现方式

## Approval Process
## 审批流程

```
AI generates proposal
AI生成提案
        ↓
Show to user
展示给用户
        ↓
User approves / rejects
用户批准/拒绝
        ↓
[Approved] → AI executes → Record to evolution log
[批准] → AI执行 → 记录到进化日志

[Rejected] → AI notes reason → Wait for next trigger
[拒绝] → AI记录原因 → 等待下次触发
```

## Execution Rules
## 执行规则

1. **Backup before change**
   变更前先备份

2. **Follow proposal exactly**
   严格按照提案执行

3. **Update evolution log**
   更新进化日志

4. **Test if possible**
   尽量测试

5. **Report to user**
   向用户汇报结果
