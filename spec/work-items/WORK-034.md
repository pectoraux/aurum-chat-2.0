# WORK-034 — Agent Gateway and Runtime

## Objective

Implement provider-independent agent execution infrastructure separate from persistent Agent Workforce state.

## Dependencies

WORK-022, WORK-031, WORK-002.

## Scope

- Agent Gateway contract;
- provider/runtime adapters;
- execution context;
- permission-scoped tool access;
- asynchronous execution;
- retries;
- idempotency;
- execution result normalization;
- usage/cost metadata;
- evidence/result capture;
- cancellation and timeout semantics.

## Acceptance Criteria

1. Agent definitions can execute through a provider-independent gateway.
2. Multiple agent providers/runtimes can implement the same gateway contract.
3. Provider SDKs do not leak into domain modules.
4. Agent permissions are enforced before tool/action execution.
5. Agent executions are traceable and asynchronous.
6. Retries cannot duplicate non-idempotent actions.
7. Execution results are normalized independently of provider.
8. Completed executions retain provider/runtime metadata for auditability.
9. Agent runtime can be swapped without changing the Agent Workforce domain model.
