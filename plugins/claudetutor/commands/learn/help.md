---
name: learn:help
description: Show available claudetutor commands and usage
allowed-tools: []
---

# /learn:help

## claudetutor Commands

| Command | Description |
|---------|-------------|
| `/learn:changes` | Learn from uncommitted code changes |
| `/learn:pr <url>` | Learn from a pull request |
| `/learn:flow <file>` | Trace and learn a code flow |
| `/learn:quiz` | Take an adaptive quiz |
| `/learn:review` | Review spaced repetition cards |
| `/learn:debug` | Debugging challenge |
| `/learn:codereview` | Practice writing code reviews on real diffs |
| `/learn:status` | View learning progress |
| `/learn:help` | Show this help |

## Learning Modes

- **Explain mode**: Claude explains the change clearly and concisely
- **Challenge mode**: Socratic dialog where Claude guides you with questions
- **Quiz mode**: Adaptive questions testing your understanding
- **Debug challenge**: Find subtle bugs in modified code
- **Code review**: Practice reviewing real diffs and get scored on completeness, accuracy, tone, and actionability

## Data Storage

- Global: `~/.claudetutor/` (cards, state)
- Per-project: `.claudetutor/` (project-specific cards, progress history)
