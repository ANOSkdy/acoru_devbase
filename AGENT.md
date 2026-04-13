# AGENT.md

## Purpose
This repository is developed primarily through AI-assisted implementation.
This file defines the non-negotiable engineering rules for safe, minimal, reproducible changes.

## Default Stack
- Deploy: Vercel
- Framework: Next.js App Router + TypeScript
- Package manager: pnpm only
- Runtime: Node.js first
- Database: Neon Postgres
- AI: Gemini Flash via server-side only
- Primary users: desktop-first internal/business users
- UX requirement: mobile-optimized baseline must still be maintained

## Core Development Principles
- Keep diffs minimal.
- Do not refactor unrelated areas.
- Do not introduce large abstractions unless clearly necessary.
- Preserve build stability at all times.
- Preserve GitHub -> Vercel deployment compatibility.
- Prefer the smallest dependency set that satisfies the task safely.
- Default to implementation that is easy to review, easy to revert, and easy to operate.

## Package / Tooling Rules
- Use pnpm only.
- Never use npm or yarn.
- Keep lockfile consistent and reproducible.
- Pin versions when the repo policy requires exact versions.
- Do not hand-edit lockfiles.
- Do not add postinstall/prebuild hooks that trigger hidden side effects.
- Avoid adding lint/build tooling unless required by the repo baseline.

## Runtime Rules
- Prefer Node runtime.
- Use Edge only when explicitly requested and compatibility is confirmed.
- Any route that touches DB or secret-bearing services must run on Node runtime.
- Do not move secret-bearing logic to client components.

## Environment / Secret Safety
- Never expose secrets to the client.
- Never use `NEXT_PUBLIC_*` for DB or AI secrets.
- Never inject secrets through `next.config`.
- Keep DB access server-only.
- Keep AI access server-only.
- Avoid logging raw secrets or full connection strings.
- Prefer `.env.example` for documenting required variables.

## Database Rules
- Primary DB is Neon Postgres via server-only env.
- Prefer `DATABASE_URL`; fallback may use `NEON_DATABASE_URL` if the repo supports it.
- Use parameterized SQL only.
- Validate all inputs before DB access.
- Do not instantiate DB connections eagerly at import time.
- DB modules must be safe even when env vars are missing.
- Missing DB env should not break build unless the feature explicitly requires it.
- Migrations must be explicit and safe to re-run when designed as idempotent.

## API Rules
- Validate params, query, and body with zod or equivalent schema validation.
- Return structured JSON errors.
- Keep error messages concise and safe.
- Do not leak stack traces, secrets, or raw infrastructure details.
- For App Router dynamic route handlers, use current-safe typing patterns compatible with the repo’s Next.js version.
- Avoid unsupported route exports and outdated route typing patterns.

## UI / UX Rules
- Mobile-first responsive baseline is required, even if the primary use is desktop.
- Use semantic HTML.
- Keep layouts simple, readable, and accessible.
- Avoid hover-only interaction.
- Ensure forms have labels, helpful validation, and visible focus states.
- Prefer straightforward admin/business UI over decorative complexity.

## Data Fetching Rules
- Do not fetch your own Route Handlers from server-rendered build paths unless there is a strong reason.
- Do not make the default homepage depend on DB connectivity during build.
- Avoid self-fetch patterns that create build or deployment instability.
- Prefer server components, route handlers, and server actions where appropriate and safe.
- Keep build-time rendering independent of unavailable runtime secrets whenever possible.

## AI Feature Rules
- Only implement AI features when explicitly requested.
- Use Gemini via server-side calls only.
- Never expose AI API keys to the client.
- Do not add AI SDK dependencies unless AI is part of the requested scope.
- Validate and sanitize inputs to AI calls when user input is involved.
- Keep prompts/config server-side.

## Quality Gates
Every change must aim to preserve a clean deployable state.

Required unless the repo explicitly says otherwise:
- `pnpm install --frozen-lockfile`
- `pnpm typecheck`
- `pnpm build`

If lint is configured, it must also pass.

## Scope Discipline
- Implement only what is requested in specs and task instructions.
- Do not add speculative features.
- Do not rename or move large parts of the project without explicit request.
- Prefer small, reviewable PRs.
- If a requested change conflicts with existing specs, follow the newest explicit instruction and update the relevant spec files in the same PR.

## Source of Truth Order
When implementing, read in this order:
1. direct task instruction
2. AGENT.md
3. DESIGN.md
4. docs/product-scope.md
5. relevant files in `specs/**`
6. existing codebase constraints

If there is conflict, prefer the most recent and most specific source.

## Required Behavior for AI Contributors
Before making changes:
- read the relevant spec files
- identify the minimum file set to touch
- avoid unrelated edits
- preserve build stability
- update specs when behavior changes

After making changes:
- verify type/build expectations as appropriate
- ensure no secrets were exposed
- ensure the diff remains minimal
- ensure new screens/routes are reflected in specs if needed
