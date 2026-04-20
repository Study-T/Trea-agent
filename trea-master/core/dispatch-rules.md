# Dispatch and Communication Rules
# 调度与通信规则

## Role Hierarchy
## 角色层级

```
Boss (老板)
└── 调度 → PM组长 / RD组长 / QA组长
          └── 调度 → 各组专员
```

## Dispatch Rules
## 调度规则

| 角色 | 可调度对象 |
|-----|-----------|
| Boss | 只能调度组长 |
| 组长 | 调度自己组内专员 |
| 专员 | 不能调度任何人 |

## Dispatch Triggers
## 调度触发条件

### Boss Dispatch Triggers
### Boss调度触发

| 触发条件 | Boss行为 | 说明 |
|---------|---------|------|
| 用户提交新需求 | Boss接收需求，理解后分配给PM组长 | PM阶段开始 |
| PM阶段通过Boss审核 | Boss立即分配给RD组长 | RD阶段开始 |
| RD阶段通过Boss审核 | Boss立即分配给QA组长 | QA阶段开始 |
| QA阶段通过Boss审核 | Boss输出完成报告给用户 | 流程结束 |
| 任意阶段被Boss拒绝 | Boss打回给当前组长 | 该阶段需重做 |

### Leader Dispatch Triggers
### 组长调度触发

| 触发条件 | 组长行为 | 说明 |
|---------|---------|------|
| 收到Boss分配的任务 | 组长开始调度第一个专员 | 阶段开始 |
| 当前专员完成输出 | 组长立即调度下一个专员 | 按顺序执行 |
| 专员报告数据缺失 | 组长汇总所有请求后上报Boss | 暂停调度，等待数据 |
| 所有专员完成 | 组长汇总全部输出，提交给Boss | 等待Boss审核 |
| Boss拒绝该阶段 | 组长重新分配给相关专员 | 按错误包返工 |

### Specialist Dispatch Triggers
### 专员调度触发

| 触发条件 | 专员行为 | 说明 |
|---------|---------|------|
| 收到组长分配任务 | 立即开始工作 | 执行自己的分析/设计/实现 |
| 完成工作 | 主动向组长报告完成 | 数据传递给后序专员 |
| 发现数据缺失 | 立即报告组长，等待数据 | 不能自行编造数据 |
| 收到返工指令 | 根据错误包重新执行 | 完成当前工作 |

### Sequential Execution Rule
### 顺序执行规则

**重要：专员必须按顺序执行，前一个专员完成后才能调度下一个。**

| 场景 | 规则 |
|------|------|
| 当前专员未完成 | 不能调度下一个专员 |
| 当前专员输出不合格 | 返工完成后才能继续 |
| 数据缺失 | 暂停，等待Boss从用户获取数据 |

## Communication Rules
## 通信规则

| 角色 | 可通信对象 |
|-----|-----------|
| Boss | 组长 + 用户（仅限需求接收和数据请求） |
| 组长 | 和Boss + 同组专员通信 |
| 专员 | 只能和同组专员通信 |

## Boss Special Responsibilities
## Boss特殊职责

Boss是用户与工作流之间的唯一接口：

```
用户需求 → Boss → PM组长
Boss ← 数据请求 ← 组长（汇总后）
Boss → 数据请求 → 用户（汇总后）
Boss → 下一阶段 ← 上一阶段通过
```

| 场景 | Boss行为 |
|------|---------|
| 接收用户需求 | Boss直接接收，理解后分配给PM组长 |
| 组长报告数据缺失 | Boss汇总后直接联系用户获取数据 |
| 阶段通过审核 | Boss直接分配下一阶段 |
| 阶段被拒绝 | Boss打回给当前组长 |

## Cross-Group Communication
## 跨组通信

不同组需要通信时，必须通过上级中转：

```
PM专员A 想联系 RD专员B
        ↓
PM专员A → PM组长 → Boss → RD组长 → RD专员B
```

## Within-Group Data Flow
## 组内数据流转

同组专员之间可以自由传递数据，按执行顺序进行：

```
专员1 → 专员2 → 专员3 → ... → 组长汇总
```

| 场景 | 传递方式 |
|------|---------|
| 专员→后序专员 | 直接传递，注明来源和目的 |
| 专员→组长 | 汇总后统一提交 |
| 数据缺失 | 专员→组长（汇总）→Boss→用户 |

### Within-Group Data Template
### 组内数据传递模板

```markdown
## Data Exchange / 数据交换
- **From**: [Specialist A]
- **To**: [Specialist B]
- **Data Type**: [input/output/requirement]
- **Content**: [summary of data]
```

### Leader Collection Template
### 组长汇总模板

```markdown
## [Phase] Leader Collection / [阶段]组长汇总
- **Specialists Count**: N
- **Data Requests**: [list of any missing data]
- **Outputs**: [consolidated output summary]
```

## Communication Diagram
## 通信示意图

```
        Boss
       / | \
   PM组长 RD组长 QA组长
   /|\    /|\    /|\
  专员   专员   专员
```

Note: No direct lines between leaders. All cross-group communication goes through Boss.
注意：组长之间没有直接连线。所有跨组通信通过Boss中转。

## Data Authenticity Rules
## 数据真实性规则

**严禁推测、判断、推断、预测任何虚假信息，所有数据必须是真实的。**

| 角色 | 数据真实性要求 |
|-----|--------------|
| Boss | 向用户传递的信息必须基于真实数据，严禁编造或推测用户需求 |
| 组长 | 汇总的数据必须来自专员真实输出，严禁自行补充未经验证的信息 |
| 专员 | 所有分析、设计、实现必须基于真实数据和事实，严禁推测或编造数据 |

| 场景 | 正确行为 | 错误行为 |
|------|---------|---------|
| 数据缺失 | 立即上报，等待真实数据 | 自行推测或编造数据 |
| 信息不确定 | 明确标注"待确认"，上报获取 | 凭印象或推断给出结论 |
| 需要额外信息 | 通过层级上报请求用户提供 | 假设或猜测缺失信息 |

## Rules
## 规则

1. Boss cannot communicate directly with specialists
   Boss不能直接和专员通信

2. Leaders cannot communicate with leaders of other groups
   组长之间不能直接通信

3. Specialists can only communicate within their own group
   专员只能在同组内通信

4. All cross-group communication must go through hierarchy
   所有跨组通信必须通过层级中转

5. All data must be real and verifiable, strictly prohibit speculating, inferring, or predicting false information
   所有数据必须是真实的、可验证的，严禁推测、推断或预测虚假信息
