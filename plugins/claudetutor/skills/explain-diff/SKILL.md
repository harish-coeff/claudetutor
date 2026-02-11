---
name: explain-diff
description: Explain a code diff block clearly and concisely. Used by tutor-teacher agent during explain mode in /learn:changes and /learn:pr.
user-invocable: false
---

# Explain Diff Skill

Given a diff block, explain:
1. **What changed**: Describe the modification in plain language
2. **Why it matters**: Explain the purpose and impact
3. **Key concept**: Identify the core programming concept
4. **Context**: How it connects to the rest of the codebase
5. **Gotchas**: Any subtle aspects or potential issues

Keep explanations to 2-3 key points. Use code examples from the diff.

For Socratic challenge mode, see `references/socratic-method.md`.
