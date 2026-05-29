---
name: using-deep-reviewer-seek
description: 在任何对话开始时使用——建立如何查找和使用技能，在任何回应（包括澄清问题）之前要求Skill工具调用
---

<SUBAGENT-STOP>
如果你被派遣为子Agent执行特定任务，跳过此技能。
</SUBAGENT-STOP>

<EXTREMELY-IMPORTANT>
如果你认为某个技能有哪怕1%的可能适用于你正在做的事情，你绝对必须调用该技能。

如果一个技能适用于你的任务，你没有选择。你必须使用它。

这不可协商。这不可选择。你不能合理化你的方式绕过。
</EXTREMELY-IMPORTANT>

## 指令优先级

deep-reviewer-seek技能覆盖默认系统提示行为，但**用户指令始终优先**：

1. **用户的显式指令**（CLAUDE.md、直接请求）— 最高优先级
2. **deep-reviewer-seek技能** — 在冲突处覆盖默认系统行为
3. **默认系统提示** — 最低优先级

## 如何访问技能

**在 Claude Code 中：** 使用 `Skill` 工具。当你调用一个技能时，其内容被加载并呈现给你——直接遵循它。绝不使用 Read 工具读取技能文件。

**在 Copilot 中：** 没有 `Skill` 工具。直接使用 `read_file` 读取 `skills/` 目录下对应的 SKILL.md 文件。读取后直接遵循其内容。

# 使用技能

## 规则

**在任何回应或行动之前调用相关或被请求的技能。** 哪怕1%的可能某个技能适用，意味着你应该调用该技能检查（Claude Code 用 Skill 工具，Copilot 用 read_file）。如果调用的技能证明对当前情况不适用，你不需要使用它。

## 可用技能

本插件提供以下审查相关技能：

**审查流程：**
- `requesting-code-review` — 结构化代码/计划/设计/项目审查，包含需求覆盖矩阵
- `receiving-code-review` — 处理审查反馈，需要技术严谨而非表演性同意

**测试与质量：**
- `test-driven-development` — 红-绿-重构循环，好测试长什么样
- `verification-before-completion` — 永远证据先于断言
- `systematic-debugging` — 根源分析技术

**工作流：**
- `brainstorming` — 审查前理解需求，探索代码应该做什么
- `writing-plans` — 从批准的spec编写实现计划

**元技能：**
- `using-deep-reviewer-seek` — 本技能（框架引导）

## 技能类型

**刚性** (TDD, verification-before-completion)：严格遵循。不要为了变通而偏离纪律。

**柔性** (brainstorming, writing-plans)：根据上下文调整原则。

技能本身会告诉你它是哪类。

## 用户指令

指令说的是做什么（WHAT），而非怎么做（HOW）。"审查这个"或"检查这段代码"不意味着跳过工作流。

## 红线

这些想法意味着停止——你在合理化：

| 想法 | 现实 |
|------|------|
| "这只是一个简单审查" | 简单代码也有bug。检查技能。 |
| "我需要更多上下文" | 技能检查在澄清问题之前。 |
| "让我先探索代码库" | 技能告诉你如何探索。先检查。 |
| "我记得这个技能" | 技能在演化。阅读当前版本。 |
| "这不需要正式技能" | 如果技能存在，使用它。 |
| "技能是大材小用" | 简单的东西变复杂。使用它。 |
| "我先做这一件事" | 在做任何事之前检查。 |
