# ADR-0012 — Provider Isolation

## Status

Accepted

## Decision

LLM, search, messaging, telephony, storage, and other vendors are hidden behind application-owned interfaces.

## Rationale

Vendor choices must remain replaceable and must not leak into domain logic.

## Consequence

Domain modules cannot import provider SDKs directly.
