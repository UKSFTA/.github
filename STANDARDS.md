# UKSFTA Development Standards

Technical standards for all UKSFTA repositories. This document covers code,
licensing, assets, and publishing. For contribution process, see
[CONTRIBUTING.md](CONTRIBUTING.md). For security, see [SECURITY.md](SECURITY.md).

## Code Standards

### General

- Write clear, self-documenting code.
- Comment **why**, not what.
- No dead code, commented-out code, or debug artefacts.
- No secrets, credentials, or API keys in code.
- British English in all documentation and comments (defence, colour, behaviour).

### Commit Standards

All commits must be GPG-signed. Format per [CONTRIBUTING.md](CONTRIBUTING.md):

- Subject: imperative mood, under 72 characters, no full stop.
- Body: what and why, not how. Wrap at 72 characters.
- Reference issues where applicable.

### Language Standards

| Language | Standards |
| --- | --- |
| Python | Type hints, docstrings, ruff formatting, pyproject.toml |
| JavaScript/TypeScript | ESLint, consistent style, .nvmrc for Node version |
| C# (.NET) | Nullable annotations, XML doc comments, .editorconfig |
| Bash | ShellCheck clean, POSIX-compatible where possible |
| Hugo/HTML | WCAG 2.1 AA, semantic HTML, alt text on all images |

## Licensing

UKSFTA uses three licence types. Each repository must have a `LICENSE` file in
its root.

### Arma 3 Mods and Assets

Use the **Arma Public License (APL)** for all Arma 3 mods, maps, templates,
scripts, and Zeus content.

- Attribution required.
- Noncommercial use only.
- Applies to: UKSFTA-Mods, UKSFTA-Maps, UKSFTA-Template, UKSFTA-Scripts,
  UKSFTA-Zeus, UKSFTA-COP.

Reference: https://www.bohemia.net/community/licenses/arma-public-license

### Software and Tooling

Use **MIT** for all non-Arma software: bots, libraries, DevOps tooling, web
portals.

- Permissive. Allows reuse by other communities.
- Attribution required (included in licence text).
- Applies to: UKSFTA-Tools, UKSFTA-Bot, UKSFTA-BIS, UKSFTA.github.io.

### Forked Software

Forks retain the **original licence**. Do not re-licence forks.

- UKSFTA-AOL: GPL-2.0 (forked, cannot re-licence).

### Adding New Repositories

Choose the licence before creating the repo:

| Content Type | Licence |
| --- | --- |
| Arma 3 mod, map, or asset | APL |
| Software, library, or tool | MIT |
| Fork of existing project | Original licence |

## Asset Ownership

### UKSFTA-Created Assets

All code, mods, maps, templates, and scripts created by UKSFTA members are
owned by the UKSFTA development team. They are published under the licence
stated in the repository's `LICENSE` file.

### Third-Party Assets

Do not commit third-party assets (RHS, CUP, 3CB, BAF, etc.) to UKSFTA
repositories. Reference them as dependencies or requirements:

- In README: list required third-party mods with links.
- In code: use CfgPatches `requiredAddons` for Arma dependencies.
- Never include third-party PBOs, textures, or models.

### Asset Provenance

When adding assets to a repository, document their origin:

- Who created them.
- When they were created.
- Which third-party assets they depend on.
- Which licence applies.

## Publishing and Releases

### Versioning

Use [Semantic Versioning](https://semver.org/) for all software:

- **MAJOR** (X.0.0): Breaking changes to APIs or file formats.
- **MINOR** (0.X.0): New features, backwards-compatible.
- **PATCH** (0.0.X): Bug fixes, no API changes.

Arma mods may use Arma 3 version conventions where appropriate (e.g., game
version compatibility).

### Release Process

1. All CI checks must pass before release.
2. Create a GitHub release with:
   - Tag matching the version number.
   - Release notes summarising changes.
   - Built artefacts attached (where applicable).
3. Releases are signed where the build pipeline supports it.

### Changelogs

Maintain a `CHANGELOG.md` in each repository that makes releases. Format:

```
## [version] - YYYY-MM-DD

### Added
- New features.

### Changed
- Changes to existing functionality.

### Fixed
- Bug fixes.

### Removed
- Removed features.
```

## CI/CD Expectations

All repositories must have:

- **CodeQL** analysis (or equivalent SAST) on push and PR.
- **Gitleaks** secrets scanning on push and PR.
- **Branch protection** on the default branch (required reviews, no force push).

Additional checks by repository type:

| Repository | Additional CI |
| --- | --- |
| UKSFTA-Tools | ruff lint, pytest |
| UKSFTA-Bot | ESLint, npm test |
| UKSFTA-BIS | dotnet build, dotnet test |
| UKSFTA-AOL | ShellCheck, Bats tests |
| UKSFTA.github.io | Hugo build, HTML validation, axe accessibility |

## Documentation

Every repository must have:

- **README.md**: What it does, how to use it, how to contribute.
- **LICENSE**: The licence file.
- **AGENTS.md** (where applicable): AI agent instructions for the repository.

Optional but recommended:

- **CHANGELOG.md**: Release history.
- **CONTRIBUTING.md**: Override or extend org-level guidelines.
- **.github/ISSUE_TEMPLATE/**: Custom issue templates.

## Enforcement

These standards are enforced through:

- Branch protection rules (require reviews, status checks).
- CI pipelines (linting, testing, security scanning).
- CODEOWNERS (review requirements).
- Pull request reviews (manual verification).

Non-compliant pull requests will not be merged. Repeated violations may result
in loss of commit access.
