---
name: learn:quiz
description: Take an adaptive quiz on recently learned code concepts. Use when the developer wants to test their understanding.
allowed-tools: [Read, Glob, Grep, Write]
---

# /learn:quiz

## Objective

Test the developer's understanding through adaptive quiz questions.

## Step 1: Load Context

Read recent learning history from `.claudetutor/progress/history.jsonl`.
Identify concepts learned in the last 7 days.

## Step 2: Generate Questions

Use tutor-quizzer agent to generate questions:
- 5 questions for quick mode, 10 for full
- Types: what-does-this-do, multiple-choice, fill-in-code, spot-the-bug, free-response
- Start at difficulty 3 (see `skills/generate-quiz/references/difficulty-levels.md`)

## Step 3: Administer Quiz

For each question:
1. Present the question
2. Collect the answer
3. Score (auto for multiple-choice, Claude for free-response on 0-100 scale)
4. Show feedback explaining the correct answer
5. Adjust difficulty

### Adaptive Difficulty Rules

- Correct + fast (< 30s): difficulty += 0.3
- Correct + slow (>= 30s): difficulty += 0.1
- Wrong: difficulty -= 0.5
- Clamp between 1 and 5
- Target ~70% correct rate

## Step 4: Record Results

Save quiz session to `.claudetutor/progress/history.jsonl`.
Update concept mastery scores.
