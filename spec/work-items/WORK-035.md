# WORK-035 — General-Purpose Extension Runtime

## Objective

Implement the runtime capabilities required to host real applications, not only stateless functions.

## Dependencies

WORK-003, WORK-022.

## Scope

- versioned extension manifest;
- isolated execution;
- persistent scoped state;
- host-rendered/declarative UI;
- scheduled triggers;
- event subscriptions;
- scoped external participants/access;
- quotas/resource controls;
- lifecycle state;
- deployment/disablement/rollback;
- invocation/outcome telemetry;
- compatibility/version enforcement.

## Acceptance Criteria

1. An extension can persist tenant/install-scoped records.
2. A real extension can render declarative UI surfaces without arbitrary host script access.
3. An extension can execute a named export on a schedule.
4. An extension can subscribe to approved system events.
5. An extension can support authorized external participants without access to the Aurum knowledge graph.
6. Resource quotas and concurrency controls are enforced.
7. Manifest/API versions are explicit and compatible.
8. Existing stateless extension execution remains supported.
9. Extension executions are isolated and auditable.
10. A fixture extension demonstrates state + UI + schedule + event subscription + scoped access.

## Security

No extension may cross its install, tenant, permission, or sandbox boundary.
