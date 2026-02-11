---
name: trace-flow
description: Trace code execution flow from an entry point through imports and function calls. Used by /learn:flow command.
user-invocable: false
---

# Trace Flow Skill

Given an entry point file or function:
1. Identify the starting point
2. Follow imports and function calls
3. For each step, explain:
   - What the module/function does
   - How data transforms
   - Key design decisions
4. Build an ASCII concept map of relationships
5. Limit depth to 5 levels unless otherwise specified
