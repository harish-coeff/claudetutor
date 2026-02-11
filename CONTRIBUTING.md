# Contributing to claudetutor

Thank you for your interest in contributing to claudetutor.

## Overview

claudetutor is a Claude Code plugin built with markdown files. You can edit files and test immediately — no build step required.

## Project Structure

```
claudetutor/
├── .claude-plugin/
│   └── marketplace.json             Marketplace catalog
└── plugins/claudetutor/             The plugin
    ├── .claude-plugin/plugin.json   Plugin manifest
    ├── commands/learn/              Slash command definitions (/learn:*)
    ├── agents/                      Agent definitions (tutor-teacher, etc.)
    └── skills/                      Reusable skill definitions with references
        ├── explain-diff/            Diff explanation + Socratic method reference
        ├── generate-quiz/           Quiz generation + difficulty levels reference
        ├── trace-flow/              Code flow tracing
        └── data-model/              Learning data schema reference
```

## How to Modify

### Commands (`plugins/claudetutor/commands/learn/*.md`)

Each file defines a `/learn:*` slash command. Format:

```markdown
---
name: learn:commandname
description: Short description. Include when this command should be used.
allowed-tools: [Read, Glob, Grep, Bash, Write]
argument-hint: <optional-arg>
---

# Prompt content

Instructions for Claude when the user runs this command.
```

Key frontmatter fields:
- `name` — slash command name
- `description` — what it does and when to use it (helps Claude match user intent)
- `allowed-tools` — tools pre-approved without permission prompts
- `argument-hint` — shown during autocomplete

### Agents (`plugins/claudetutor/agents/*.md`)

Agent definitions with specialized behaviors. Each file is a markdown prompt that defines an agent's personality and capabilities.

### Skills (`plugins/claudetutor/skills/*/SKILL.md`)

Reusable capabilities for agents. Each skill lives in its own directory with:
- `SKILL.md` — main skill definition
- `references/` — supporting reference documents (loaded on demand)

Skills with `user-invocable: false` are background knowledge — not shown in the `/` menu but available to agents.

## Testing Locally

Add the marketplace and install from your local directory:

```
/plugin marketplace add /path/to/your/claudetutor
/plugin install claudetutor
```

Then use any `/learn:*` command inside Claude Code to test your changes.

## Pull Request Guidelines

1. Keep PRs focused on a single change
2. Test your changes locally
3. Write clear commit messages describing what and why
4. Update the relevant command/agent/skill markdown if you change behavior

## Questions?

Open an issue on GitHub for bugs, feature requests, or questions.
