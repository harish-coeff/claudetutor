---
name: learn:flow
description: Trace and learn a code flow from an entry point through the codebase. Use when the developer wants to understand how code executes across files.
allowed-tools: [Read, Glob, Grep]
argument-hint: <file-or-function>
---

# /learn:flow

## Objective

Help the developer understand how code flows from an entry point through the codebase.

## Step 1: Identify Entry Point

Read the specified file. Identify the main export or entry function.

## Step 2: Trace Imports

Follow import statements to build a dependency graph.
Limit depth to 5 levels.

## Step 3: Step-Through

For each step in the flow:
1. Read the file
2. Explain what the module/function does
3. Show how data transforms
4. Highlight design decisions

## Step 4: Concept Map

Generate an ASCII concept map showing:
- Files/modules as nodes
- Import/call relationships as edges
- Data flow direction

## Step 5: Quiz and Cards

Generate questions about the flow and create spaced repetition cards.
See `skills/data-model/SKILL.md` for card format.

## Usage

```
/learn:flow src/auth/login.ts
```
