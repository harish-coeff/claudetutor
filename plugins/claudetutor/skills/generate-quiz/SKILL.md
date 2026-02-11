---
name: generate-quiz
description: Generate adaptive quiz questions from recently learned code. Used by tutor-quizzer agent during /learn:quiz and post-learning quizzes.
user-invocable: false
---

# Generate Quiz Skill

Generate quiz questions from the provided code context:
1. Create questions of varied types (what-does-this-do, multiple-choice, fill-in, spot-the-bug, free-response)
2. Target the specified difficulty level (1-5, see `references/difficulty-levels.md`)
3. Focus on conceptual understanding, not syntax memorization
4. Each question should have:
   - Clear question text
   - Relevant code snippet (if applicable)
   - Correct answer
   - Explanation of why
5. Return as structured JSON
