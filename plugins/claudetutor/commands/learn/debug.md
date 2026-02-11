---
name: learn:debug
description: Practice debugging with AI-generated challenges based on code you have learned. Use when the developer wants to sharpen debugging skills.
allowed-tools: [Read, Glob, Grep, Write]
---

# /learn:debug

## Objective

Build debugging skills through challenges where a subtle bug is introduced into code the developer has recently learned.

## Process

1. **Select code**: Pick a recently learned code block from `.claudetutor/progress/history.jsonl`.
2. **Introduce bug**: Create a subtle, realistic bug (off-by-one, missing null check, stale closure, wrong variable reference, race condition, etc.).
3. **Present**: Show the buggy code and ask the developer to find the bug.
4. **Hints**: Provide progressive hints if stuck:
   - **Vague**: General area ("The bug is related to how data is processed")
   - **Directional**: Points toward it ("Look at the loop condition on line X")
   - **Specific**: Nearly reveals it ("The comparison operator should be <= not <")
5. **Score**: Rate the developer's debugging approach (0-5).
6. **Record**: Save challenge results to `.claudetutor/progress/history.jsonl`.
