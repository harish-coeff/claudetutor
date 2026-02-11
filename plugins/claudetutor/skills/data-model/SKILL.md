---
name: data-model
description: Schema reference for claudetutor learning data — card format, history log, state file. Used by all /learn:* commands when reading or writing learning data.
user-invocable: false
---

# Data Model

## Directory Structure

```
~/.claudetutor/              Global (cross-project)
├── cards/                   Spaced repetition cards (*.md)
└── STATE.md                 Global learning state

.claudetutor/                Per-project
├── cards/                   Project-specific cards (*.md)
└── progress/
    └── history.jsonl        Learning event log
```

## Card Format

Each card is a Markdown file with YAML frontmatter in `cards/`:

```markdown
---
question: "What does the useEffect cleanup function do in this hook?"
answer: "It unsubscribes from the WebSocket connection to prevent memory leaks."
codeSnippet: |
  useEffect(() => {
    const ws = new WebSocket(url);
    return () => ws.close();
  }, [url]);
concept: "react-hooks-cleanup"
difficulty: 3
easeFactor: 2.5
interval: 1
repetitions: 0
nextReviewDate: "2026-02-12"
created: "2026-02-11"
---

## Context

This pattern prevents WebSocket connections from leaking when the component
unmounts or when the `url` dependency changes.
```

### SM-2 Fields

| Field | Type | Description |
|-------|------|-------------|
| `easeFactor` | float | Starts at 2.5, adjusted after each review (min 1.3) |
| `interval` | int | Days until next review |
| `repetitions` | int | Consecutive correct recalls |
| `nextReviewDate` | string | ISO date (YYYY-MM-DD) |

## history.jsonl

Append-only log in `.claudetutor/progress/history.jsonl`. One JSON object per line:

```jsonl
{"type":"block_learned","timestamp":"2026-02-11T10:30:00Z","command":"learn:changes","concept":"react-hooks-cleanup","score":85,"difficulty":3}
{"type":"quiz_completed","timestamp":"2026-02-11T10:35:00Z","command":"learn:quiz","score":80,"difficulty":3.3,"questionsCorrect":4,"questionsTotal":5}
{"type":"review_completed","timestamp":"2026-02-11T10:40:00Z","command":"learn:review","cardsReviewed":3,"cardsCorrect":2}
{"type":"debug_challenge","timestamp":"2026-02-11T10:45:00Z","command":"learn:debug","concept":"off-by-one","score":4,"hintsUsed":1}
{"type":"codereview_completed","timestamp":"2026-02-11T10:50:00Z","command":"learn:codereview","completeness":75,"accuracy":90,"tone":85,"actionability":70}
```

### Event Types

| Type | Fields |
|------|--------|
| `block_learned` | concept, score, difficulty |
| `quiz_completed` | score, difficulty, questionsCorrect, questionsTotal |
| `review_completed` | cardsReviewed, cardsCorrect |
| `debug_challenge` | concept, score, hintsUsed |
| `codereview_completed` | completeness, accuracy, tone, actionability |

## STATE.md

Global state file at `~/.claudetutor/STATE.md`:

```markdown
# claudetutor State

Current streak: 5 days
Due today: 3
Last session: 2026-02-11
Total blocks learned: 42
```
