# Project Lifecycle

This document defines the standard end-to-end flow for AI-assisted implementation.

## Standard flow
1. **Requirement intake**
   - Capture business goal, in-scope, out-of-scope, and constraints.
2. **Product scope update**
   - Update `docs/product-scope.md` with the latest project boundaries.
3. **Spec definition/update**
   - Create or update relevant files in `specs/**` as implementation source of truth.
4. **Codex task creation**
   - Write a task prompt that references specs and constraints (not a full re-write of all context).
5. **Implementation**
   - Implement with minimal diff and no unrelated refactor.
6. **PR review**
   - Review spec/code alignment, scope discipline, and operational safety.
7. **Spec alignment in same PR**
   - If behavior changed, update affected specs in the same PR.
8. **Optional human-facing doc refresh**
   - Update architecture or design docs when long-lived patterns changed.

## Operating rules
- Keep PRs small and reviewable.
- Keep spec updates and behavior changes in the same PR whenever possible.
- Do not merge implementation that contradicts specs without spec updates.
- Prefer incremental changes over broad rewrites.

## Done criteria
A change is done when:
- behavior is implemented as requested,
- related specs are current,
- review checklist passes,
- and deployment safety constraints remain intact.
