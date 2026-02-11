---
name: learn:status
description: View learning progress, streaks, and areas needing attention. Use when the developer wants to check their learning dashboard.
allowed-tools: [Read, Glob]
---

# /learn:status

## Objective

Show the developer their learning progress, streaks, and areas needing attention.

## Process

1. **Load data**: Read from `.claudetutor/progress/` and `~/.claudetutor/`.
2. **Compute stats**: Current streak, total blocks learned, quiz scores, concept mastery.
3. **Show weak areas**: Concepts with mastery < 0.6.
4. **Due reviews**: Number of spaced repetition cards due.
5. **Recommendations**: Suggest next learning actions based on weak areas and due reviews.

See `skills/data-model/SKILL.md` for data storage format.
