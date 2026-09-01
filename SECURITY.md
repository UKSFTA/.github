# Security Policy

## Supported Versions

Security updates apply to the current major version of all UKSFTA projects.
Older versions receive critical fixes only.

| Project | Supported |
| --- | --- |
| UKSFTA-Tools | Current release |
| UKSFTA-Bot | Current release |
| UKSFTA-BIS | Current release |
| UKSFTA.github.io | Current deployment |
| All other repos | Best-effort |

## Reporting a Vulnerability

We take security seriously. If you discover a vulnerability, do **not** open a
public issue.

### How to Report

1. **GitHub Security Advisory** (preferred): Use the "Report a vulnerability"
   button on the Security tab of the affected repository.
2. **Direct contact**: Message UKSFTA Leadership via Discord or GitHub.

### What to Include

- Description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

### Response Timeline

- **Acknowledgement**: Within 48 hours
- **Triage**: Within 7 days
- **Fix or mitigation**: Depends on severity, typically within 30 days

### Disclosure Policy

We follow coordinated disclosure. We will work with you to understand and
address the issue before any public disclosure. We request 90 days from
reporting to release a fix.

## Security Measures

All UKSFTA repositories enforce:

- GPG-signed commits (where branch protection is enabled)
- Automated security scanning (CodeQL, Semgrep)
- Branch protection rules on default branches
- Dependency updates via Dependabot

## Scope

This policy covers all repositories under the [UKSFTA](https://github.com/UKSFTA)
organisation. For issues specific to the Arma 3 mod environment (server-side
only), contact leadership directly.
