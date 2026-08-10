---
name: cross-framework-error-message-update
description: Workflow command scaffold for cross-framework-error-message-update in xyflow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /cross-framework-error-message-update

Use this workflow when working on **cross-framework-error-message-update** in `xyflow`.

## Goal

Synchronize or update error messages across both React and Svelte packages, ensuring consistency and framework-specific messaging.

## Common Files

- `packages/react/src/components/Handle/index.tsx`
- `packages/react/src/hooks/useStore.ts`
- `packages/react/src/index.ts`
- `packages/react/src/store/initialState.ts`
- `packages/react/src/utils/edges.ts`
- `packages/react/src/utils/index.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit error message logic in React files (e.g., components, utils, store).
- Edit error message logic in Svelte files (e.g., components, utils, store).
- Update shared system files if error message constants or utilities are involved.
- Optionally update or add changeset files for changelog tracking.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.