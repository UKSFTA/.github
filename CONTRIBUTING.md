# Contributing to UKSFTA

Thank you for contributing to UKSFTA. This guide covers the standards and
processes for all repositories in the organisation.

## Prerequisites

1. A GitHub account with two-factor authentication enabled.
2. GPG key added to your GitHub account (for signed commits).
3. Familiarity with the repository's AGENTS.md (where present).

## Getting Started

1. Fork the repository or create a branch from `main`.
2. Make your changes in small, focused commits.
3. Each commit must be GPG-signed.
4. Open a pull request against `main`.

## Commit Standards

All commits must follow these rules:

- **Subject line**: Imperative mood, under 72 characters, no full stop.
  - Good: `add input validation for user reports`
  - Bad: `Fixed the bug` / `Update README.md`
- **Body**: Explain what and why, not how. Wrap at 72 characters.
- **Signed**: Every commit must have a GPG signature (`git commit -S`).
- **Linked**: Reference the issue number where applicable (`fixes #123`).

### Commit Format

```
<short summary under 72 chars>

<optional body, wrapped at 72 chars>

<optional footer: fixes #issue, per standard ref>
```

## Pull Request Process

1. Fill in the PR template completely.
2. Ensure all CI checks pass.
3. Request at least one review from a maintainer.
4. Address review feedback with new commits (do not force-push during review).
5. Squash and merge once approved.

### PR Requirements

- One logical change per PR. Do not bundle unrelated changes.
- Include tests for new functionality.
- Update documentation where applicable.
- No merge conflicts with `main`.

## Code Standards

### General

- Write clear, self-documenting code.
- Comment **why**, not what.
- No dead code, commented-out code, or debug artefacts.
- No secrets, credentials, or API keys in code.

### Language-Specific

| Repository | Language | Standards |
| --- | --- | --- |
| UKSFTA-Tools | Python | Type hints, docstrings, ruff formatting |
| UKSFTA-Bot | JavaScript/Node.js | ESLint, consistent style |
| UKSFTA-BIS | C# (.NET) | Nullable annotations, XML doc comments |
| UKSFTA-AOL | Bash | ShellCheck clean, POSIX-compatible where possible |
| UKSFTA.github.io | Hugo/HTML | Accessibility (WCAG 2.1 AA), semantic HTML |

### Documentation

- Use British English spelling (defence, colour, behaviour).
- Write in plain language. Avoid jargon where a simple term works.
- Keep READMEs focused: what it does, how to use it, how to contribute.

## Issue Guidelines

- Use the provided issue templates.
- Be specific: steps to reproduce, expected behaviour, actual behaviour.
- Label issues appropriately (bug, enhancement, documentation, etc.).

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](CODE_OF_CONDUCT.md).
By participating, you agree to abide by its terms.

## Questions?

Open a discussion in the relevant repository or ask in the UKSFTA Discord
development channel.
