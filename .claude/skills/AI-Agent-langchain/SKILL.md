```markdown
# AI-Agent-langchain Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the AI-Agent-langchain Python codebase. It covers coding conventions, commit patterns, and step-by-step workflows for releasing new versions and implementing features or bugfixes with proper test coverage. The repository follows clear naming conventions, structured commit messages, and encourages test-driven development.

## Coding Conventions

- **File Naming:**  
  Use `snake_case` for all Python files.
  ```
  # Good
  agent_core.py
  integration_utils.py

  # Bad
  AgentCore.py
  integrationUtils.py
  ```

- **Import Style:**  
  Use relative imports within packages.
  ```python
  # Good
  from .utils import parse_input

  # Bad
  import utils
  ```

- **Export Style:**  
  Use named exports; avoid wildcard imports.
  ```python
  # Good
  __all__ = ["Agent", "AgentManager"]

  # Bad
  from module import *
  ```

- **Commit Messages:**  
  - Use prefixes like `fix:`, `feat:`, or `release:`  
  - Keep messages concise (~60 characters)
  ```
  feat: add support for multi-agent coordination
  fix: resolve memory leak in agent manager
  release: bump version to 1.2.0
  ```

## Workflows

### Library Release Version Bump
**Trigger:** When releasing a new version after merging features or fixes  
**Command:** `/release`

1. Update the version number in `pyproject.toml` for the relevant package:
    ```toml
    [tool.poetry]
    version = "1.2.0"
    ```
2. Update the version in `__init__.py` if present:
    ```python
    __version__ = "1.2.0"
    ```
3. Update lock files (`uv.lock`) if dependencies have changed.
4. Summarize key changes in the commit message:
    ```
    release: bump version to 1.2.0 with new agent features
    ```
5. Commit all changes and push to the repository.

**Files Involved:**
- `libs/*/pyproject.toml`
- `libs/*/__init__.py`
- `libs/*/uv.lock`

### Feature or Fix with Targeted Tests
**Trigger:** When adding a new feature or fixing a bug, ensuring it is covered by tests  
**Command:** `/feature-with-tests`

1. Modify or add implementation files in the relevant module (e.g., `core`, `middleware`, `integration`):
    ```python
    # libs/agent_core/agent.py
    class Agent:
        ...
    ```
2. Add or update unit test files in the corresponding `tests/unit_tests/` directory:
    ```python
    # libs/agent_core/tests/unit_tests/test_agent.py
    def test_agent_initialization():
        agent = Agent()
        assert agent.is_ready()
    ```
3. Describe the change, rationale, and test plan in the commit message:
    ```
    feat: add agent readiness check
    - Added is_ready() method to Agent
    - Covered by test_agent_initialization
    ```
4. Commit both implementation and test changes together.

**Files Involved:**
- `libs/*/*/*.py`
- `libs/*/tests/unit_tests/**/*.py`

## Testing Patterns

- **Test File Location:**  
  Tests are placed under `libs/<module>/tests/unit_tests/`.
- **Test File Naming:**  
  Use `test_*.py` for Python unit tests.
- **Test Framework:**  
  Not explicitly specified; likely `pytest` or similar.
- **Example Test:**
  ```python
  def test_feature_enabled():
      result = feature.is_enabled()
      assert result is True
  ```

## Commands

| Command              | Purpose                                               |
|----------------------|-------------------------------------------------------|
| /release             | Bump library version after new features or fixes      |
| /feature-with-tests  | Add feature or fix with corresponding unit tests      |
```
