# Contributing to aX Agent Studio

Thanks for your interest in improving aX Agent Studio. This repository is
public-facing, so changes should be easy for contributors to understand, test,
and review.

## Code of Conduct

This project is governed by our [Code of Conduct](./CODE_OF_CONDUCT.md). By
participating, you are expected to uphold it. Report unacceptable behavior to
**support@ax-platform.com**.

## Getting Started

### Prerequisites

- **Python 3.13+**
- **[uv](https://github.com/astral-sh/uv)** package manager
- **Git**

### Fork & Clone

1. Fork this repository on GitHub
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/ax-agent-studio.git
   cd ax-agent-studio
   ```
3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/ax-platform/ax-agent-studio.git
   ```

## Development Setup

```bash
uv sync
python --version  # Should show Python 3.13+
```

### Pre-commit Hooks

```bash
pre-commit install
pre-commit run --all-files  # optional, verify setup
```

Hooks run Ruff (lint + format), mypy, and Bandit automatically on each commit.

### Manual Quality Checks

```bash
ruff check .
ruff format .
mypy src/
bandit -r src/ -c pyproject.toml
```

### Run the Dashboard

```bash
python scripts/start_dashboard.py
```

Open http://127.0.0.1:8000 to verify it works.

### Run Tests

```bash
python tests/test_message_parsing.py
python tests/test_gemini_e2e.py
```

## Branches

- `main` is the production branch.
- Create feature or fix branches from `main`.
- All changes go through a reviewed PR.

## Commit Style

Use Conventional Commits:

- `feat:` for new features or monitor types
- `fix:` for bug fixes
- `docs:` for documentation changes
- `test:` for adding or updating tests
- `refactor:` for code refactoring
- `perf:` for performance improvements
- `chore:` for maintenance tasks

Example:

```
feat: Add Anthropic Claude support to langgraph monitor

Added Claude integration using langchain-anthropic.
Supports Claude Opus, Sonnet, and Haiku models.

Closes #123
```

## Security and Credentials

aX Agent Studio handles MCP connections, API keys, and agent configurations.
Treat credentials carefully:

- Do not log or print raw API keys or tokens.
- Do not commit `.env` files, agent configs with real credentials, or secrets.
- Agent-to-agent communication should use scoped MCP tool access.
- Update tests and docs for any authentication or credential behavior change.

## Contributor License Agreement (CLA)

Before we can accept your first pull request, you must sign our CLA. This is
handled automatically by the CLA Assistant bot on GitHub. When you open your
first PR, the bot will post a comment with a sign link. You only need to sign
once. Without a signed CLA, the PR cannot be merged.

## Pull Request Guidelines

Before submitting:

- Code runs without errors
- Pre-commit hooks pass (`pre-commit run --all-files`)
- Tests pass
- No sensitive data committed
- Branch is up to date with `main`

PR description should include:

- **What** changed
- **Why** it was needed
- **How** to test it
- **Screenshots** for UI changes

## Community & Support

- **GitHub Issues**: [Report bugs or request features](https://github.com/ax-platform/ax-agent-studio/issues)
- **Security Vulnerabilities**: See [SECURITY.md](./SECURITY.md) — do not open a public issue
- **Discussions**: [Ask questions, share ideas](https://github.com/ax-platform/ax-agent-studio/discussions)

## License

By contributing to aX Agent Studio, you agree that your contributions will be
licensed under the **MIT License**.
