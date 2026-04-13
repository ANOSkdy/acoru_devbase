# ADR 0002: Neon Postgres via Server-Only Access

## Status
Accepted

## Context
The project requires a hosted Postgres-compatible database compatible with Vercel deployment and safe secret handling.

## Decision
Use Neon Postgres through server-only environment variables and server-side access paths.

## Consequences
- No client-side DB access
- Stronger secret isolation
- Simpler deployment model for internal/business apps
