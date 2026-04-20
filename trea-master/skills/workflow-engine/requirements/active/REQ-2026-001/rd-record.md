# REQ-2026-001 - RD Phase Record
# REQ-2026-001 - RD阶段记录

## Record Information
## 记录信息

| Field | Value |
|-------|-------|
| Requirement ID | REQ-2026-001 |
| Phase | RD |
| Phase Start | 2026-04-20 17:10:00 |
| Phase End | - |
| Iteration Count | 1 (进行中) |
| Status | 🔄 In Progress |
| Prerequisites | PM Phase ✅ Completed |

## RD Leader Output
## RD组长输出

基于本地代码仓库分析，发现完整架构已存在：

### 核心发现
1. **QueryBNPLHomeStatus接口已存在**（credit_prod.thrift L3368）
   - 请求：WalletUserId
   - 响应：CreditStatus + AvailableAmount
2. **wallet_operation投放编排层已存在**（SpaceId=8001, BizLine=BNPL）
   - Completer链：region补参→状态补参→白名单→风控→实验→物料组装
3. **wallet_home调用层已存在**（TTPayFinanceEntryLoader）
   - 调用GetMaterial获取BNPL物料，注入pageCtx

### BNPL系统侧（credit_prod）开发步骤
- Step 1: 确认QueryBNPLHomeStatus是否支持VN/MY市场
- Step 2: 扩展市场支持（如需要）
- Step 3: 确认/扩展返回字段
- Step 4: 自测验证

### 代码位置
| 文件 | 职责 | 项目 |
|------|------|------|
| ttpay_finance_entry_loader.go | Wallet Home调用pipo.wallet.operation获取BNPL物料 | wallet_home |
| bnpl_ttpay_home_completer.go | TTPay首页补参：region/credit_status/available_amount | wallet_operation |
| bnpl_entrance_show_allowlist_decision_completer.go | 风控白名单预检 | wallet_operation |
| bnpl_entrance_show_risk_decision_completer.go | 风控决策+用户分组 | wallet_operation |
| bnpl_entrance_schema_completer.go | AB实验分组匹配+Schema选择 | wallet_operation |
| query_bnpl_home_status_handler.go | BNPL系统侧接口实现 | credit_prod |

### Specialists Involved
### 参与的专员

| # | Specialist | Output Summary |
|---|------------|---------------|
| 1 | 01-tech-requirement | 技术目标：BNPL PSM入口数据接口；约束：Native/投放系统/TCC |
| 2 | 02-business-logic | 5步业务流程；2种用户状态×市场条件分支；纯读取链路 |
| 3 | 03-project-query | 发现本地代码仓库：credit_prod/wallet_operation/wallet_home |
| 4 | 04-api-doc | QueryBNPLHomeStatus IDL已存在；GetMaterial接口已存在 |
| 5 | 05-tech-design | 三层架构：Native→pipo.wallet.home→BNPL PSM |
| 6 | 06-database-design | 纯读取链路，依赖已有表credit_apply_order/credit_limit |
| 7 | 07-data-flow | 纯读取链路，无需分布式事务，降级show_entry=false |
| 8 | 08-coding-standards | Go/Kitex/Thrift/TCC/Starling |
| 9 | 13-dependency | pipo.wallet.home/BNPL PSM/投放系统/Starling均为已有服务 |

## Boss Review
## Boss审核

| Field | Value |
|-------|-------|
| Reviewer | Boss |
| Review Date | - |
| Result | 🔄 Pending |

## Record Timestamp
## 记录时间戳

- **Recorded at**: 2026-04-20 17:30:00 (部分记录，RD阶段尚未完成)
- **Recorded by**: Boss (Trae Master)
- **Confirmation**: RD Leader 🔄 / Boss 🔄 / User 🔄
