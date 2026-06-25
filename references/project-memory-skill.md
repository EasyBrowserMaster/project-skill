# PROJECT_MEMORY_SKILL.md

## Purpose

本 Skill 用于解决 AI Agent 切换后丢失上下文的问题。

目标：

* 保留长期项目记忆
* 保留技术决策
* 保留失败经验
* 支持 Claude、Codex、Cursor、Gemini 等 Agent 共享上下文

---

# Startup Workflow

进入项目后必须按顺序执行：

1. 阅读 `.ai/AGENTS.md`
2. 阅读 `.ai/DECISIONS.md`
3. 阅读 `.ai/MEMORY.md`
4. 阅读 `.ai/HANDOFF.md`
5. 阅读 `.ai/FAILED_ATTEMPTS.md`

禁止在未阅读上述文件前直接开始分析项目。

---

# File Responsibilities

## AGENTS.md

项目永久规则。

包含：

* 项目目标
* 架构说明
* 编译命令
* 目录结构
* 编码规范
* 不允许修改的内容

特点：

长期稳定。

---

## MEMORY.md

项目知识库。

记录：

* 关键发现
* 调试结果
* 逆向分析结果
* 技术结论

格式：

### 日期

问题：

发现：

结论：

影响：

---

## DECISIONS.md

记录重要决策。

格式：

Decision ID:

日期：

决定：

原因：

替代方案：

影响：

目标：

避免未来 Agent 重复推翻已经验证过的决策。

---

## HANDOFF.md

当前任务状态。

包含：

* 当前目标
* 已完成内容
* 当前阻塞
* 下一步计划
* 推荐接手动作

特点：

短期内容。

每次工作结束必须更新。

---

## FAILED_ATTEMPTS.md

记录失败方案。

格式：

日期：

目标：

尝试方案：

失败原因：

结论：

禁止重复尝试条件：

目标：

避免未来重复踩坑。

---

# Before Any Major Change

执行以下检查：

1. 是否与 DECISIONS.md 冲突
2. 是否与 MEMORY.md 冲突
3. 是否属于 FAILED_ATTEMPTS.md 已失败方案

若冲突：

必须说明原因。

禁止直接覆盖历史结论。

---

# End Of Session Workflow

工作结束前必须：

更新：

* MEMORY.md
* DECISIONS.md
* HANDOFF.md
* FAILED_ATTEMPTS.md（如有）

---

# Handoff Template

## Current Goal

当前任务

## Completed

已完成

## Current Findings

当前发现

## Blockers

当前阻塞

## Next Steps

下一步建议

## Files Modified

修改文件

## Notes

特别注意事项

---

# Agent Rules

Agent 应优先：

* 复用已有结论
* 复用已有设计
* 复用已有经验

Agent 不应：

* 重复分析已解决问题
* 重复尝试已失败方案
* 推翻已有决策而不给出理由

项目知识优先级：

DECISIONS.md
↓
MEMORY.md
↓
HANDOFF.md
↓
源码分析

若源码与历史记录冲突：

先分析原因，再做修改。
