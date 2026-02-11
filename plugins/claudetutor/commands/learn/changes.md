---
name: learn:changes
description: Learn from uncommitted code changes through explanation or Socratic challenge. Use when the developer wants to understand their recent modifications before committing.
allowed-tools: [Read, Glob, Grep, Bash, Write]
---

# /learn:changes

## Objective

Help the developer deeply understand their uncommitted code changes through active learning.

## Step 1: Gather Changes

```bash
git diff
git diff --cached
```

Combine both outputs.

## Step 2: Parse and Classify

- Group changes by file
- Skip files matching: `*.lock`, `*.min.*`, `node_modules/`, `dist/`
- Classify each block: feature, bugfix, refactor, test, config, docs, style, dependency

## Step 3: Order Blocks

Priority: feature > bugfix > refactor > test > others
Within same classification: smaller changes first (fewer lines = easier to learn)

## Step 4: Block-by-Block Learning

For each block:

1. Show the diff with file path and change type
2. Ask: "Would you like me to **explain** this change, or would you prefer to **figure it out** yourself?"
3. **Explain mode**: Provide a clear, concise explanation covering:
   - What changed and why
   - Key concept demonstrated
   - Connection to the rest of the codebase
   - Potential gotchas
4. **Challenge mode**: Use the Socratic method (see `skills/explain-diff/references/socratic-method.md`):
   - Show the old code and surrounding context
   - Ask questions to guide understanding
   - Provide progressive hints if stuck (vague → directional → specific)
   - Only reveal after 3+ attempts or explicit request
5. Record completion

## Step 5: Quiz

Generate 5-10 quiz questions from learned blocks using tutor-quizzer agent:
- Adaptive difficulty targeting 70% correct rate (see `skills/generate-quiz/references/difficulty-levels.md`)
- Score free-response answers

## Step 6: Create Spaced Repetition Cards

For each learned block, create a card in `.claudetutor/cards/`:
- Key concept as the question
- Code snippet from the diff
- Explanation as the answer
- Schedule first review for tomorrow (interval: 1 day)

See `skills/data-model/SKILL.md` for card format.

## Step 7: Record Progress

Append learning events to `.claudetutor/progress/history.jsonl`.
Update `~/.claudetutor/STATE.md`.
