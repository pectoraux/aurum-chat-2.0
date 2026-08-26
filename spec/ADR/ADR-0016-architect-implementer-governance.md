# ADR-0016 — Architect / Implementer Separation

## Status

Accepted

## Decision

The architect owns frozen architecture and review. z.ai implements bounded WORK items.

## Rationale

Separating architecture ownership from implementation reduces architectural drift and makes review adversarial rather than self-certifying.

## Consequence

z.ai cannot silently redefine architecture. Architectural discoveries requiring change must enter an explicit change process.
