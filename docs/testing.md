# Testing Code Review Plugin

This document describes how to test the code review plugin skills.

## Test Structure

```
tests/
└── claude-code/
    ├── test-helpers.sh                    # Shared test utilities
    ├── test-document-review-system.sh     # Tests spec document reviewer
    ├── analyze-token-usage.py             # Token analysis tool
    └── README.md                          # Test documentation
```

## Running Tests

```bash
cd tests/claude-code
./test-document-review-system.sh
```

## Requirements

- Claude Code CLI installed and in PATH (`claude --version` should work)
- Must run from the plugin directory
- Local dev marketplace enabled: `"deep-reviewer-seek@deep-reviewer-seek-dev": true` in `~/.claude/settings.json`

## Token Analysis Tool

Analyze token usage from any Claude Code session:

```bash
python3 tests/claude-code/analyze-token-usage.py ~/.claude/projects/<project-dir>/<session-id>.jsonl
```

## Writing New Tests

1. Create test file: `tests/claude-code/test-<skill-name>.sh`
2. Source `test-helpers.sh`
3. Write tests using `run_claude` and assertions
4. Make executable: `chmod +x test-<skill-name>.sh`
