# PR Review Checklist

Use this to review AI-assisted implementation PRs.

## Scope and diff discipline
- [ ] Change matches requested scope.
- [ ] No unrelated refactor or speculative changes.
- [ ] Diff is minimal and revert-friendly.
- [ ] Non-scope / untouched areas are clearly stated.

## Spec and behavior alignment
- [ ] Behavior aligns with referenced specs.
- [ ] Relevant specs were updated in same PR when behavior changed.
- [ ] If spec update is marked unnecessary, reason is explicit and valid.

## Technical governance
- [ ] Runtime choice is appropriate (Node first; Edge only when justified).
- [ ] Secret-bearing logic remains server-side only.
- [ ] New routes/pages (if any) are declared and reviewed.
- [ ] Build/type checks are reported.
