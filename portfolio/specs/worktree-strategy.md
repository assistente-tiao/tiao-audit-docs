# Git / Worktree Execution Strategy

## Goal
Allow safe parallel execution of implementation cards without file collisions or ambiguous ownership.

## Branch Pattern
- `feat/{task-id}-{slug}`

## Default Rule
- One active implementation card per branch/worktree.
- Specs and scaffolding cards may be sequential in main workspace if no parallelism is needed.

## File Ownership
- A task owns only the files listed in its acceptance criteria or task definition.
- Cross-cutting file edits require explicit dependency or follow-up card.
- Shared files (like config or core README) should be touched by the earliest owning card only.

## Conflict Protocol
1. If two tasks need the same file, do not run them in parallel.
2. Split the work or serialize by dependency.
3. If unavoidable, nominate one owning task and make the other depend on it.

## Commit Rule
- Commit at task-complete granularity.
- No mixed-purpose commits spanning unrelated cards.

## Merge Rule
- A branch merges only after acceptance criteria are satisfied.
- No merge if it weakens contracts defined earlier.

## Practical V1 Execution
- Current project is mostly spec-first; parallel execution can start later when implementation cards emerge.
- Until then, keep execution serialized by Kanban dependency order.
