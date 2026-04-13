# Architecture

## Overview
This system is built with Next.js App Router and TypeScript, deployed via GitHub -> Vercel.
The primary database is Neon Postgres accessed from server-side code only.

## Main Components
- Web UI
- Route Handlers / server logic
- Server-only DB access layer
- Optional AI integration layer
- Optional background or scheduled jobs if explicitly requested

## Runtime Policy
- Node runtime first
- Edge only when explicitly requested and verified compatible
- DB and secret-dependent logic must remain on Node/server-side paths

## Data Access
- DB access occurs only from server-side modules
- Parameterized SQL only
- Input validation before data access
- Avoid client-side DB access patterns entirely

## AI Access
- Gemini is called from server-side code only
- API keys remain server-only
- AI is optional and should not be introduced unless explicitly requested

## Deployment Model
- GitHub -> Vercel
- Production / Preview / Development environments
- Environment variables managed per environment
- No secret injection to client bundles

## Build Safety
- Build should not fail simply because runtime DB env is absent unless the page/feature explicitly requires it
- Avoid self-fetch from server-rendered paths during build/prerender
- Keep homepage and public entry screens build-safe by default

## Folder Intent
- `app/`: routes, pages, route handlers
- `lib/`: reusable server/client utilities
- `components/`: UI components
- `scripts/`: explicit utilities such as migrations
- `migrations/`: SQL migrations
- `docs/`: human and AI-readable repository guidance
- `specs/`: functional source-of-truth specs for implementation

## Change Policy
When architecture-relevant changes are introduced:
- update this file if the change is long-lived
- update the relevant `specs/**`
- keep the implementation aligned with AGENT.md and DESIGN.md
