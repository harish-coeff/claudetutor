# claudetutor

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Claude Code plugin that helps you learn deeply from your code changes.

## The Problem

Research shows AI coding tools reduce developer comprehension by up to 17%, with debugging as the most impaired skill. Developers who passively accept AI-generated code lose the ability to understand, debug, and reason about their own codebase.

## The Solution

claudetutor makes developers actively learn from code changes through multi-modal pedagogy — all inside Claude Code as `/learn:*` slash commands.

## Install

Inside Claude Code, run:

```
/plugin marketplace add https://github.com/harish-coeff/claudetutor
/plugin install claudetutor
```

## Commands

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
| `/learn:help` | Show available commands |

## How It Works

claudetutor is a prompt-driven plugin. Each command contains instructions that Claude follows to deliver a learning experience. There are no compiled scripts or deterministic algorithms — Claude reads your code, generates explanations and questions, and adapts to your responses in real time.

### Learning Modes

- **Explain mode** — Claude explains what each code change does and why, filling gaps in your understanding.
- **Challenge mode** — Socratic dialog where Claude guides you with targeted questions about changes.
- **Adaptive quizzes** — Test understanding with difficulty that adjusts to your performance.
- **Debugging challenges** — Find bugs introduced into code you have learned.
- **Code review** — Practice reviewing real diffs and get scored on completeness, accuracy, tone, and actionability.
- **Spaced repetition** — SM-2 algorithm ensures you remember what you learn, surfacing cards at optimal intervals.
- **Concept mapping** — Shows relationships between code concepts.

### Data Storage

All learning data is stored locally as plain text (Markdown + YAML frontmatter + JSONL). No database, no cloud sync.

| Location | Scope | Contents |
|----------|-------|----------|
| `~/.claudetutor/` | Global | Spaced repetition cards, learning state |
| `.claudetutor/` | Per-project | Project-specific cards, progress history |

## Example

```
> /learn:changes

Claude reads your uncommitted diff and groups changes by file.

For each change block:
  "This adds a retry wrapper around the HTTP client.
   Would you like me to explain this change,
   or would you prefer to figure it out yourself?"

> figure it out

  "What problem do you think this code is trying to solve?"

> handling transient network failures

  "Exactly. Now look at the backoff calculation — what happens
   after the third retry attempt?"

...after all blocks, Claude generates a quiz and creates
spaced repetition cards for key concepts.
```

## Security

claudetutor runs entirely within Claude Code's permission model. The Write tool is used only to save learning data to `.claudetutor/` and `~/.claudetutor/` directories. The Bash tool is used only for `git` and `gh` CLI commands to read diffs and PR data.

## Prerequisites

- [Claude Code](https://claude.com/claude-code) installed and authenticated (`claude login`)

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

MIT
