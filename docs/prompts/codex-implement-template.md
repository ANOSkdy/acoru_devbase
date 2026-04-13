# Codex Implementation Prompt Template

Implement the requested change by following these sources of truth in order:

1. AGENT.md
2. DESIGN.md
3. docs/product-scope.md
4. relevant files in specs/**

## Task
[Describe the requested implementation in 1-3 bullets.]

## Files to Read
- [specs/features/...]
- [specs/screens/...]
- [specs/api/...]
- [specs/data-model/...]

## Rules
- minimal diff only
- pnpm only
- preserve clean build
- preserve GitHub -> Vercel compatibility
- Node runtime for DB/secret-bearing routes
- zod validation for request validation
- parameterized SQL only
- do not expose secrets to client or logs
- do not refactor unrelated areas
- add only the minimal files needed

## Acceptance
- feature works as described
- pnpm typecheck passes
- pnpm build passes
- no secret exposure
- specs are updated if behavior changed

## Output
Return code changes only.
Keep the diff minimal and production-safe.
