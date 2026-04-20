# REQ-2026-001: [BNPL]TTPay首页新增BNPL入口
# REQ-2026-001: Add BNPL Entry Point to TTPay Homepage

## Basic Information
## 基本信息

| Field | Value |
|-------|-------|
| Requirement ID | REQ-2026-001 |
| Title | [TikTok Pay][User Portal][VN/MY/TH/PH] Add BNPL Entry Point to User Portal Homepage |
| Created Date | 2026-04-20 16:30:00 |
| Created By | Boss (Trae Master) |
| Status | Active |
| Priority | P0 (High) |
| Meego ID | 6864371595 |
| Project Key | 5f4dfa14f4a2962fbd546404 (国际支付/Global Payment) |
| Business Line | TikTok Pay (PIPO-GPB → BNPL) |

## Requirement Summary
## 需求概要

在 TikTok Pay (TTPay) User Portal 首页新增 BNPL 入口，覆盖 VN/MY/TH/PH 四个市场。用户通过该入口可直接进入 BNPL 服务（授信/账单/还款等），提升 BNPL 产品的可发现性和用户转化率。

## Requirement Details
## 需求详情

### 核心需求
- 在 TTPay User Portal Homepage 新增 BNPL 入口卡片/图标
- 覆盖市场：VN、MY、TH、PH
- 入口需根据用户 BNPL 状态（未授信/已授信/已支用等）展示不同内容
- 需接入投放系统，支持灰度、实验、白名单等配置化能力

### Meego 信息
- PRD文档: https://bytedance.sg.larkoffice.com/docx/ZioDdW7s8ods9PxdBjblGSXTg2r
- 当前状态: 开发中
- 当前节点: Server开发&自测 / iOS审核风险排查 / QA Case design / Data Analysis / Risk signoff / 隐私评估

### 团队角色
| Role | Name | Email |
|------|------|-------|
| PM | Han Yang Lim | han.lim@bytedance.com |
| Tech Owner | 胡正康 | huzhengkang@bytedance.com |
| Server | 胡正康 | huzhengkang@bytedance.com |
| iOS | 闫晗 | yanhan.yanhan@bytedance.com |
| Android | 王凯 | wangkai.rd@bytedance.com |
| QA | 朱辉荣/陆璐/王博 | zhuhuirong/lulu.brzs/wangbo.lmnd |
| DA | 李芯晨 | lixinchen.geyc@bytedance.com |
| UED | 王晨珉 | wangchenmin.5173@bytedance.com |

### 关联需求
| Meego ID | Title | Status | Relation |
|----------|-------|--------|----------|
| 6888639098 | 【投放】TTPay首页BNPL入口接入投放 | 待资源评估 | 配套投放需求 |
| 6083669866 | 【BNPL-ID】BNPL Entrance on TikTok Pay Homepage | 待资源评估 | ID市场参考实现 |

## Acceptance Criteria
## 验收标准

- [ ] TTPay首页展示BNPL入口，覆盖VN/MY/TH/PH四国
- [ ] 入口根据用户BNPL状态展示差异化内容
- [ ] 入口点击跳转至正确的BNPL服务页面
- [ ] 投放系统接入完成，支持灰度/实验/白名单
- [ ] 多语言文案配置完成
- [ ] 埋点方案实施并验证
- [ ] QA测试通过，无P0/P1缺陷

## Notes
## 备注

- ID市场已有类似实现（Meego ID: 6083669866），可参考其技术方案
- 投放系统接入为独立需求（Meego ID: 6888639098），需协同推进
- 当前需求在Meego中状态为"开发中"，Server开发&自测阶段已开始
