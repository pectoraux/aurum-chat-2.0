# WORK-032 — Source and Connector Framework

## Objective

Implement the provider-independent source/connector boundary for internal and external information ingestion.

## Dependencies

WORK-005, WORK-006, WORK-003.

## Scope

- source definitions;
- connector contracts;
- authorization/scope;
- webhook and polling modes;
- checkpoints/cursors;
- reliability metadata;
- rate limits;
- deduplication;
- retry;
- replay/reprocessing;
- raw artifact references;
- ingestion execution identity.

## Acceptance Criteria

1. A source can be registered without coupling domain code to its provider.
2. Connector adapters can ingest through webhooks and/or polling where supported.
3. Duplicate delivery does not create duplicate authoritative observations.
4. Checkpoints are durable and recoverable.
5. Failed ingestion is retryable.
6. Historical raw artifacts can be replayed/reprocessed without rewriting original observations.
7. Source authorization and scope are enforced server-side.
8. Provider-specific connector types cannot leak into domain contracts.

## Out of Scope

- semantic claim/belief interpretation;
- environment impact analysis;
- chat channel UX.
