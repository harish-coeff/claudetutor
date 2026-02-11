# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 0.1.x   | :white_check_mark: |

## Reporting a Vulnerability

If you discover a security vulnerability, please report it responsibly.

**Do not open a public GitHub issue for security vulnerabilities.**

Instead, please email security@claudetutor.dev with:

- A description of the vulnerability
- Steps to reproduce
- Potential impact
- Suggested fix (if any)

We will acknowledge receipt within 48 hours and aim to provide a fix within 7 days for critical issues.

## Security Considerations

claudetutor is a Claude Code plugin that runs entirely within Claude Code's permission model:

- Does **not** collect or transmit telemetry
- All AI queries are handled by Claude Code — no separate API keys or authentication
- Stores learning data locally in `~/.claudetutor/` and `.claudetutor/`

## Scope

The following are in scope for security reports:

- Prompt injection via command definitions or agent prompts
- Unintended file read/write outside intended directories
