# Spec Authoring Guide

## Purpose of each spec type
- `specs/screens/`: screen-level UX behavior (states, user actions, layout expectations).
- `specs/features/`: feature-level behavior and business rules.
- `specs/api/`: request/response contracts, validation, and error patterns.
- `specs/data-model/`: entities, fields, relationships, and constraints.
- `specs/flows/`: end-to-end user/system workflows across multiple screens or APIs.

## Recommended writing granularity
- One spec file should cover one coherent unit of change.
- Keep files short enough for single-PR review.
- Prefer concrete behavior bullets over abstract narratives.
- Split into multiple files when independent areas can be implemented/reviewed separately.

## Acceptance criteria writing rules
Acceptance criteria should be:
- **observable** (what user/system can verify),
- **testable** (clear pass/fail),
- **bounded** (scope and non-scope are explicit),
- **implementation-agnostic when possible** (focus on outcomes).

Use this pattern:
- Given [precondition]
- When [action]
- Then [expected result]

## When to create or update each type
- Update `screens` when UI state, interaction, or visible content changes.
- Update `features` when business behavior/rules change.
- Update `api` when endpoint contract/validation/error behavior changes.
- Update `data-model` when schema-level concepts or data constraints change.
- Update `flows` when cross-screen/process sequence changes.

## Practical rule
If reviewers cannot determine expected behavior from specs alone, the specs are insufficient and should be improved before or with implementation.
