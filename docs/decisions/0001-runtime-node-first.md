# ADR 0001: Node Runtime First

## Status
Accepted

## Context
This project uses DB access and other secret-bearing server-side operations that are not universally suitable for Edge runtime.

## Decision
Default to Node runtime.
Use Edge only when explicitly requested and compatibility is verified.

## Consequences
- DB-connected routes remain safer and simpler
- Fewer runtime incompatibility surprises
- Easier handling of server-only dependencies
