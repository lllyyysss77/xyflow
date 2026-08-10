```markdown
# xyflow Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns, coding conventions, and common workflows for contributing to the `xyflow` repository. `xyflow` is a TypeScript monorepo focused on flow-based UI components, primarily using the React framework, with Svelte and a shared system package. The repository emphasizes consistency across frameworks, clear error messaging, and a structured approach to changelog management and multi-package changes.

## Coding Conventions

**File Naming**
- Use camelCase for file names.
  - Example: `useStore.ts`, `initialState.ts`

**Import Style**
- Use relative imports within packages.
  - Example:
    ```typescript
    import { getEdges } from './utils/edges';
    ```

**Export Style**
- Prefer named exports.
  - Example:
    ```typescript
    // utils/edges.ts
    export function getEdges() { ... }
    ```

**Commit Patterns**
- Types are mixed (features, fixes, chores, refactors).
- Prefixes: `chore`, `fix`, `refactor`
- Average commit message length: 48 characters.

## Workflows

### Cross-Framework Error Message Update
**Trigger:** When error messages need to be improved, clarified, or made framework-specific in both React and Svelte implementations.  
**Command:** `/update-error-messages`

1. Edit error message logic in React files (e.g., components, utils, store).
2. Edit error message logic in Svelte files (e.g., components, utils, store).
3. Update shared system files if error message constants or utilities are involved.
4. Optionally update or add changeset files for changelog tracking.

**Files Involved:**
- `packages/react/src/components/Handle/index.tsx`
- `packages/react/src/hooks/useStore.ts`
- `packages/react/src/index.ts`
- `packages/react/src/store/initialState.ts`
- `packages/react/src/utils/edges.ts`
- `packages/react/src/utils/index.ts`
- `packages/svelte/src/lib/components/NodeWrapper/NodeWrapper.svelte`
- `packages/svelte/src/lib/hooks/useStore.ts`
- `packages/svelte/src/lib/index.ts`
- `packages/svelte/src/lib/store/index.ts`
- `packages/svelte/src/lib/store/initial-store.svelte.ts`
- `packages/svelte/src/lib/utils/edges.ts`
- `packages/svelte/src/lib/utils/index.ts`
- `packages/system/src/constants.ts`
- `packages/system/src/utils/edges/general.ts`
- `packages/system/src/utils/general.ts`

**Example:**
```typescript
// packages/react/src/utils/edges.ts
export function getEdgeErrorMessage(type: string) {
  if (type === 'invalid') {
    return 'Invalid edge type for React flow.';
  }
  // ...
}
```
```typescript
// packages/svelte/src/lib/utils/edges.ts
export function getEdgeErrorMessage(type: string) {
  if (type === 'invalid') {
    return 'Invalid edge type for Svelte flow.';
  }
  // ...
}
```

---

### Add or Update Changeset
**Trigger:** When a change is made that should be tracked in the release changelog, such as a feature, fix, or breaking change.  
**Command:** `/add-changeset`

1. Create a new file in the `.changeset` directory with a descriptive name.
2. Document the nature of the change in markdown.
3. Commit the changeset file, often alongside code changes.

**Files Involved:**
- `.changeset/*.md`

**Example:**
```markdown
# .changeset/update-error-messages.md

---
"@xyflow/react": patch
"@xyflow/svelte": patch
---

Improve error messages for edge validation in both React and Svelte packages.
```

---

### Feature or Fix Cross-Package Merge
**Trigger:** When a feature or fix is ready to be merged from a topic branch into main, especially if it affects multiple frameworks.  
**Command:** `/merge-feature-branch`

1. Merge main into the feature branch if needed to resolve conflicts.
2. Update or add changeset files.
3. Update implementation files across React, Svelte, and System packages.
4. Update example or test files if relevant.
5. Commit and push the merge.
6. Merge pull request into main.

**Files Involved:**
- `.changeset/*.md`
- `packages/react/**`
- `packages/svelte/**`
- `packages/system/**`
- `examples/**`

**Example:**
```bash
git checkout feature/my-feature
git merge main
# Resolve conflicts if any
# Make code and changeset updates
git add .
git commit -m "feat: add new edge type across packages"
git push origin feature/my-feature
# Open PR and complete merge
```

## Testing Patterns

- Test files follow the `*.test.*` pattern (e.g., `useStore.test.ts`).
- The specific testing framework is not detected, but typical patterns suggest usage of Jest or similar.
- Place test files alongside implementation or in dedicated test directories.

**Example:**
```typescript
// packages/react/src/utils/edges.test.ts
import { getEdges } from './edges';

describe('getEdges', () => {
  it('returns correct edges', () => {
    // test logic
  });
});
```

## Commands

| Command                | Purpose                                                         |
|------------------------|-----------------------------------------------------------------|
| /update-error-messages | Synchronize or update error messages across frameworks           |
| /add-changeset         | Add or update a changeset file for changelog and versioning     |
| /merge-feature-branch  | Merge a feature/fix branch affecting multiple packages          |
```
