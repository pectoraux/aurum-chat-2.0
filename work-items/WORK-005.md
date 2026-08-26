# WORK-005 — Event Foundation

## Objective

Create immutable typed domain events and event persistence/dispatch foundations.

## Dependencies

WORK-004.

## Scope

Implement the event envelope, versioning, persistence, correlation/causation, and asynchronous dispatch contracts.

## Acceptance Criteria

1. Events are immutable.
2. Event types are versioned.
3. Correlation and causation are preserved.
4. Event handlers can be retried safely.
5. Duplicate delivery does not create duplicate authoritative effects where handlers are expected to be idempotent.
