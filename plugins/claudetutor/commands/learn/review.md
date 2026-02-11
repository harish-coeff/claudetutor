---
name: learn:review
description: Review spaced repetition cards that are due today. Use when the developer wants to reinforce previously learned concepts.
allowed-tools: [Read, Glob, Write]
---

# /learn:review

## Objective

Review spaced repetition cards using the SM-2 algorithm to reinforce learning.

## Process

1. **Load cards**: Read cards from `~/.claudetutor/cards/` and `.claudetutor/cards/`.
2. **Filter due**: Show only cards where `nextReviewDate <= today`.
3. **Review**: For each due card:
   - Show the question and code
   - Wait for the user to think
   - Reveal the answer
   - Ask user to rate recall quality (0-5)
4. **Update**: Apply SM-2 algorithm to update card schedule.
5. **Summary**: Show review summary and next review dates.

See `skills/data-model/SKILL.md` for card format and SM-2 fields.
