---
name: add-or-update-changeset
description: Workflow command scaffold for add-or-update-changeset in xyflow.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-changeset

Use this workflow when working on **add-or-update-changeset** in `xyflow`.

## Goal

Add or update a changeset file to document changes for release notes and versioning.

## Common Files

- `.changeset/*.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create a new file in the .changeset directory with a descriptive name.
- Document the nature of the change in markdown.
- Commit the changeset file, often alongside code changes.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.