---
name: learn:pr
description: Learn from a pull request through block-by-block analysis. Use when the developer wants to understand a PR's changes in depth.
allowed-tools: [Read, Glob, Grep, Bash, Write]
argument-hint: <pr-url>
---

# /learn:pr

## Objective

Help the developer deeply understand a pull request through active learning.

## Step 1: Fetch PR

```bash
gh pr view $ARGUMENTS --json number,title,body,author,baseRefName,headRefName,url,reviews,comments
gh pr diff $ARGUMENTS
```

## Step 2: Show Context

Display: PR title, description, author, base/head branches, review comments (if any).

## Step 3: Parse and Classify

- Group changes by file
- Skip files matching: `*.lock`, `*.min.*`, `node_modules/`, `dist/`
- Classify each block: feature, bugfix, refactor, test, config, docs, style, dependency

## Step 4: Block-by-Block Learning

Same flow as /learn:changes — for each block, offer explain or challenge mode. Include PR context (title, description, review comments) in prompts.

## Step 5: Quiz

Generate 5-10 questions specific to the PR changes using tutor-quizzer agent.

## Step 6: Create Cards and Record Progress

Create spaced repetition cards and append to `.claudetutor/progress/history.jsonl`.
See `skills/data-model/SKILL.md` for card format.

## Usage

```
/learn:pr https://github.com/org/repo/pull/42
```
