# New Project Checklist

Use this when initializing a downstream project from this standards repo.

- [ ] Repository purpose is documented as standards/governance + product implementation repo split.
- [ ] `AGENT.md`, `DESIGN.md`, `docs/product-scope.md`, `docs/architecture.md` are copied and tailored.
- [ ] `docs/process/*` and `docs/checklists/*` are copied.
- [ ] `specs/README.md` and spec templates are copied.
- [ ] `.github/pull_request_template.md` and issue templates are copied.
- [ ] Deployment path is defined as GitHub -> Vercel.
- [ ] Runtime policy is explicit (Node first; Edge only when justified).
- [ ] Secret policy is explicit (server-only env for DB/AI).
- [ ] Initial product scope and non-scope are written.
- [ ] Team agrees that specs in Markdown are implementation source of truth.
