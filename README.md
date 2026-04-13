# acoru_devbase

## What this repository is
`acoru_devbase` is a **governance and implementation-operations standard repository** for AI-assisted delivery.
It defines shared rules, process documents, and spec templates for downstream projects that use:
- GitHub -> Vercel deployment
- Next.js App Router + TypeScript
- pnpm
- Node runtime first (Edge only when explicitly justified)
- Neon Postgres (server-side only)
- Gemini (server-side only, only when explicitly in scope)

This repository is the baseline for **how to decide, specify, prompt, implement, and review**.

## What this repository is not
This is **not** an app starter template and **not** a runnable product skeleton.
It intentionally does not contain runtime application scaffolding such as:
- `app/`, `package.json`, lockfiles, or sample runtime code
- DB implementation code or migrations for a specific product
- feature-complete UI or API examples for direct deployment

## Source-of-truth policy
- Primary source of truth: `specs/**/*.md` (implementation-facing specs)
- Secondary outputs: human-facing design/overview docs (`docs/**`, `DESIGN.md`)

When conflicts happen, prefer the latest explicit task instruction, then `AGENT.md`, then specs/process docs.

## How to use this repo in a new downstream project
1. Copy/adopt the governance docs into your project (at minimum the required files listed below).
2. Fill `docs/product-scope.md` with project-specific scope and constraints.
3. Create or update relevant specs in `specs/**` before asking Codex to implement.
4. Use `docs/prompts/codex-implement-template.md` and `docs/process/prompting-policy.md` for implementation requests.
5. Keep each implementation PR small, and update specs in the **same PR** whenever behavior changes.
6. Use checklist files under `docs/checklists/` during planning and review.

## Required files for downstream adoption
At minimum, downstream repositories should keep these files aligned:
- `AGENT.md`
- `DESIGN.md`
- `docs/product-scope.md`
- `docs/architecture.md`
- `docs/process/project-lifecycle.md`
- `docs/process/spec-authoring-guide.md`
- `docs/process/prompting-policy.md`
- `docs/checklists/new-project-checklist.md`
- `docs/checklists/pre-codex-checklist.md`
- `docs/checklists/pr-review-checklist.md`
- `docs/prompts/codex-implement-template.md`
- `specs/README.md`
- relevant files in `specs/screens/`, `specs/features/`, `specs/api/`, `specs/data-model/`, `specs/flows/`
- `.github/pull_request_template.md`
- `.github/ISSUE_TEMPLATE/*.md`

## Recommended adoption pattern
- Keep this repository as your canonical policy reference.
- In each downstream product repo, copy these docs as the initial baseline.
- Evolve project-specific details in downstream specs while keeping core governance principles intact.
- Prefer minimal-diff policy updates and avoid process bloat.
