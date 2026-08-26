# ADR-0014 — PostgreSQL as Authoritative State

## Status

Accepted

## Decision

PostgreSQL is the authoritative store for application/domain state. Redis is infrastructure, not domain truth.

## Rationale

Aurum requires durable, transactional, auditable state.

## Consequence

Caches, queues, and worker state must never become the canonical source for business truth.
