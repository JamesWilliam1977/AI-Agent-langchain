---
name: library-release-version-bump
description: Workflow command scaffold for library-release-version-bump in AI-Agent-langchain.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /library-release-version-bump

Use this workflow when working on **library-release-version-bump** in `AI-Agent-langchain`.

## Goal

Bump the version of a library/package after new features or fixes are merged.

## Common Files

- `libs/*/pyproject.toml`
- `libs/*/__init__.py`
- `libs/*/uv.lock`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update the version number in pyproject.toml for the relevant package.
- Update the version number in __init__.py if present.
- Update lock files (uv.lock) if dependencies are involved.
- Summarize key changes in the commit message.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.