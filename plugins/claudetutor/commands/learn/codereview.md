---
name: learn:codereview
description: Practice writing code reviews on real diffs and get scored on completeness, accuracy, tone, and actionability. Use when the developer wants to improve review skills.
allowed-tools: [Read, Glob, Grep, Bash, Write]
---

# /learn:codereview

## Objective

Build code review skills by having the developer write a review of a real diff, then scoring it.

## Process

1. **Select a diff**: Either use recent uncommitted changes (`git diff`) or ask the user for a PR URL.
2. **Present the diff**: Show the diff clearly with file paths and context.
3. **Ask for review**: Tell the developer: "Write a code review of this diff. Comment on anything you'd flag in a real review — bugs, design issues, missing tests, performance concerns, style, etc."
4. **Score the review** using tutor-reviewer agent criteria:
   - **Completeness** (0-100): Did they catch the significant issues?
   - **Accuracy** (0-100): Are their observations correct?
   - **Tone** (0-100): Is the review constructive and professional?
   - **Actionability** (0-100): Do comments include specific suggestions?
5. **Feedback**: Show what they caught, what they missed, and tips for improvement.
6. **Record**: Save review results to `.claudetutor/progress/history.jsonl`.
