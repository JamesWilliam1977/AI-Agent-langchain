---
name: feature-or-fix-with-targeted-tests
description: Workflow command scaffold for feature-or-fix-with-targeted-tests in AI-Agent-langchain.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-fix-with-targeted-tests

Use this workflow when working on **feature-or-fix-with-targeted-tests** in `AI-Agent-langchain`.

## Goal

Implement a new feature or bugfix and add/modify corresponding unit tests in the same commit.

## Common Files

- `libs/*/*/*.py`
- `libs/*/tests/unit_tests/**/*.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Modify or add implementation files (e.g., in core, middleware, or integration folders).
- Add or update unit test files in the corresponding tests/unit_tests/ directory.
- Describe the change, rationale, and test plan in the commit message.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.