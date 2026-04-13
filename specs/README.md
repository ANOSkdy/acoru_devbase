# Specs Directory Guide

## Purpose
`specs/` contains implementation-facing source-of-truth documents used for planning, prompting, implementation, and review.

## Reading order
1. `docs/product-scope.md`
2. relevant `specs/features/*`
3. relevant `specs/flows/*`
4. relevant `specs/screens/*`
5. relevant `specs/api/*`
6. relevant `specs/data-model/*`

## How to choose which spec files to read/update
- If changing user-visible behavior, read/update `screens` and `features` first.
- If changing endpoint behavior, include `api`.
- If changing domain structure or constraints, include `data-model`.
- If changing multi-step behavior across components, include `flows`.

## Update rule
When implementation changes behavior, update related specs in the same PR.
If no spec update is needed, PR should state why.
