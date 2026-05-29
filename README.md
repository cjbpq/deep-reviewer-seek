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

**Review. Don't change.** 模型不修改你的代码。它提供审查——你决定如何处理。

## Skills Included

- `requesting-code-review` — Structured review with coverage matrix
- `receiving-code-review` — Processing feedback with technical rigor
- `test-driven-development` — What good tests look like
- `verification-before-completion` — Evidence before claims
- `brainstorming` — Understanding requirements before reviewing
- `writing-plans` — Creating implementation plans from approved specs
- `systematic-debugging` — Root cause analysis

## Installation

### GitHub Copilot（推荐）

**全局安装**（一次安装，所有项目工作区可用）：

```powershell
# 1. 克隆本仓库到本地
git clone https://github.com/cjbpq/deep-reviewer-seek.git D:\deep-reviewer-seek

# 2. 安装全局 prompt
New-Item -ItemType Directory -Force -Path "$env:APPDATA\Code\User\prompts"
Copy-Item "D:\deep-reviewer-seek\.github\prompts\deep-reviewer-seek-review.prompt.md" "$env:APPDATA\Code\User\prompts\"
```

> **为什么用绝对路径？** Copilot 不支持 Claude Code 那样的全局插件机制。`.github/` 配置只在当前工作区生效，无法跨项目。全局 prompt 通过绝对路径引用 `D:\deep-reviewer-seek\` 下的技能文件，实现在任意项目中的审查能力。

### Claude Code

作为插件安装，自动全局生效：

```bash
/plugin install D:\deep-reviewer-seek
```


### 审查输出包含

无论使用哪种方式，审查输出均包含：
- **需求覆盖矩阵** — 每个需求追溯到代码（✅/⚠️/❌）+ 证据（文件:行号）
- **问题按严重度分级** — Critical（阻塞合并）/ Important（合并前或后修复）/ Minor（不阻塞）
- **安全性评估** — 明确声明无关注点或列出具体漏洞
- **测试覆盖评估** — 覆盖缺口分析
- **明确合并裁决** — "可以合并" / "修复后合并" / "不可合并"

## License

MIT License — see LICENSE file. Based on the Superpowers project by [Jesse Vincent](https://github.com/obra).
