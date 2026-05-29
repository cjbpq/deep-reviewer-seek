---
name: deep-reviewer-seek-review
description: "Use when: reviewing code, checking PR correctness, verifying feature completeness, security audit, or any code quality assessment. Triggers the deep-reviewer-seek review workflow."
---
 read the following files from the workspace for review guidance in order:

1. .github/skills/using-deep-reviewer-seek/SKILL.md — how to use the review instruction set
2. .github/skills/requesting-code-review/SKILL.md — structured review with coverage matrix
3. AGENTS.md — review entry point and core principles

Then determine which additional skill files to read based on the review context.

For the review itself, follow the five-dimension framework defined in the skill files:
1. Completeness — every requirement traced to code
2. Correctness — logic, edge cases, error handling
3. Coherence — naming and patterns match the repo
4. Security — injection, auth, data exposure
5. Delivery — compatibility, migration, observability

Output a review with: Requirements Coverage Matrix, Issues by severity (Critical/Important/Minor), Security assessment, Clear merge verdict.
