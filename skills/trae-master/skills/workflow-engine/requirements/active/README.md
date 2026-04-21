# Active Requirements
# 活跃需求

This directory contains requirement records currently being processed.
本目录包含正在处理中的需求记录。

## Structure / 结构

Each requirement is stored as a dedicated directory:
每个需求存储为独立的目录：

```
active/
├── REQ-2026-001/
│   ├── metadata.md
│   ├── prd.md
│   ├── pm-record.md
│   ├── rd-record.md
│   ├── qa-record.md
│   └── timeline.md
├── REQ-2026-002/
└── ...
```

## Lifecycle / 生命周期

- Requirement enters this directory when Boss assigns it to a Leader
  需求在Boss分配给组长时进入此目录
- Requirement files should follow the directory-based template layout defined in `skills/workflow-engine/requirements/RECORDER_PROTOCOL.md`
  需求文件应遵循 `skills/workflow-engine/requirements/RECORDER_PROTOCOL.md` 定义的目录式模板布局
- Requirement moves to `completed/` when all phases (PM→RD→QA) pass Boss review and user confirmation
  需求在所有阶段(PM→RD→QA)通过Boss审核和用户确认后移至`completed/`
- Requirement may be removed if user chooses to abort
  需求在用户选择终止时会被移除
