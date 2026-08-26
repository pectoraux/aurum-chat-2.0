# WORK-002 — Infrastructure Foundation

## Objective

Implement the minimal authoritative persistence, cache/queue, artifact storage, and execution-context foundation.

## Dependencies

WORK-001.

## Scope

- PostgreSQL connection/persistence foundation;
- Redis infrastructure interfaces;
- object-storage interface;
- execution/correlation context;
- transaction boundary conventions;
- asynchronous job abstraction;
- health checks;
- configuration/secrets boundary.

## Acceptance Criteria

1. PostgreSQL can persist a test record transactionally.
2. Redis can support infrastructure operations without becoming domain authority.
3. Object storage can persist and retrieve a test artifact through an application-owned interface.
4. Jobs have traceable execution identity.
5. Configuration and secrets do not leak into domain modules.
6. Architecture checks remain green.

## Out of Scope

- business entities;
- observations;
- world model;
- LLM integration.
