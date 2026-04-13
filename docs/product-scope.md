# Product Scope

## Project Name
[project name]

## Objective
[What business problem this system solves.]

## Users
- Admin
- Operator
- Viewer
- [Other roles if applicable]

## In Scope
- [Authentication]
- [Dashboard]
- [Master data management]
- [Core CRUD]
- [Reporting / export]
- [AI assistance if explicitly included]

## Out of Scope
- Native mobile app
- Overly large refactors
- External integrations not explicitly defined
- Advanced analytics / BI unless requested
- Unapproved workflow expansion

## Primary Workflows
1. [User logs in]
2. [User navigates to main workflow screen]
3. [User creates/updates records]
4. [User reviews results]
5. [User exports or completes the operation]

## Business Constraints
- Internal/business users should be able to operate with low training cost
- Operational friction should be minimized
- Error recovery should be understandable to non-engineers where possible

## Technical Constraints
- Deploy on Vercel
- Next.js App Router + TypeScript
- Node runtime first
- Neon Postgres
- Gemini server-side only if AI is included
- Secrets must remain server-only
- Build and deployment reliability are prioritized

## UX Constraints
- Desktop-first business usage
- Mobile optimization required as a baseline
- Readability and speed matter more than visual flourish

## Non-Functional Expectations
- Clean build
- Type safety
- Safe secret handling
- Minimal operational complexity
- Reviewable diffs
- Reproducible installs/builds

## Success Criteria
- Core workflow works end to end
- Build/deploy succeeds cleanly
- Important inputs are validated
- Secrets are not exposed
- Users can complete the intended operation without workaround

## Notes
[Project-specific assumptions and important exclusions.]
