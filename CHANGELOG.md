# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2026-02-11

### Added

- Claude Code plugin with `/learn:*` slash commands
- Learn from uncommitted changes (`/learn:changes`)
- Learn from pull requests (`/learn:pr <url>`)
- Trace code flows (`/learn:flow <file>`)
- Adaptive quizzes with difficulty scaling (`/learn:quiz`)
- Spaced repetition with SM-2 algorithm (`/learn:review`)
- Debugging challenges (`/learn:debug`)
- Code review practice with scoring (`/learn:codereview`)
- Progress tracking with streaks and mastery stats (`/learn:status`)
- Multi-modal pedagogy: explain mode and Socratic challenge mode
- Concept mapping showing relationships between code concepts
- Local-only data storage (Markdown + YAML frontmatter + JSONL)
- Specialized agents: tutor-teacher, tutor-debugger, tutor-quizzer, tutor-reviewer
- Skills: explain-diff, generate-quiz, trace-flow, data-model
