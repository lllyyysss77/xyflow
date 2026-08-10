---
name: feature-or-fix-cross-package-merge
description: Workflow command scaffold for feature-or-fix-cross-package-merge in xyflow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-or-fix-cross-package-merge

Use this workflow when working on **feature-or-fix-cross-package-merge** in `xyflow`.

## Goal

Merge a feature or fix branch that touches multiple framework packages (React, Svelte, System), often after code review and CI.

## Common Files

- `.changeset/*.md`
- `packages/react/**`
- `packages/svelte/**`
- `packages/system/**`
- `examples/**`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Merge main into the feature branch if needed to resolve conflicts.
- Update or add changeset files.
- Update implementation files across React, Svelte, and System packages.
- Update example or test files if relevant.
- Commit and push the merge.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.