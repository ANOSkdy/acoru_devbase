# ADR 0003: Gemini via Server-Side Calls Only

## Status
Accepted

## Context
Some projects may include AI features, but key exposure and prompt/config leakage must be avoided.

## Decision
Use Gemini only through server-side calls when AI is explicitly requested.

## Consequences
- No client-side API key exposure
- Prompt/config remains controlled on the server
- AI remains optional and isolated from the default baseline
