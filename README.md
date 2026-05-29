# deep-reviewer-seek

一个全面的代码审查指令集，融合了 Superpowers 的结构化审查框架、OpenSpec 的需求追溯方法论，以及 mattpocock-skills-zh-CN 的审查风格，聚焦于一个目标：**尽可能彻底的代码审查。**

## What This Does

本仓库为 AI 编程助手提供深度代码审查指导。它从 7 个维度检查代码：

1. **Feature Completeness** — Is every requirement correctly implemented? (Most reviews skip this.)
2. **Correctness** — Logic errors, edge cases, state management, concurrency
3. **Security** — Injection, auth bypass, data exposure, input validation
4. **Code Quality** — Separation, naming, simplicity, patterns
5. **Testing** — Real behavior testing, edge case coverage, test quality
6. **Architecture** — SOLID, scalability, integration
7. **Production Readiness** — Migrations, compatibility, observability

Every review includes a **Requirements Coverage Matrix** — every stated requirement is explicitly traced to implementation code, with status (✅/⚠️/❌) and evidence (file:line).

## Core Principle

**Review. Don't change.** AI 助手不修改你的代码。它提供审查——你决定如何处理。

## Skills Included

- `requesting-code-review` — Structured review with coverage matrix
- `receiving-code-review` — Processing feedback with technical rigor
- `test-driven-development` — What good tests look like
- `verification-before-completion` — Evidence before claims
- `brainstorming` — Understanding requirements before reviewing
- `writing-plans` — Creating implementation plans from approved specs
- `systematic-debugging` — Root cause analysis

## Installation

**Copilot（推荐）：** 在 Copilot 启用的工作区中打开本仓库，Copilot 自动读取 `AGENTS.md` 及 `skills/` 下的说明文件。

**Claude Code：** 作为插件安装：
```bash
/plugin install D:\deep-reviewer-seek
```

## Usage

直接要求 AI 助手审查代码：

> "审查这个分支的最新变更"

> "检查这个 PR 是否正确实现了认证系统 spec"

> "审查这个文件的安全性和功能正确性"

审查输出包含：
- 需求覆盖矩阵
- 按严重度分级的问题（Critical / Important / Minor）
- 安全性评估
- 测试覆盖评估
- 明确合并裁决

## License

MIT License — see LICENSE file. Based on the Superpowers project by [Jesse Vincent](https://github.com/obra).
