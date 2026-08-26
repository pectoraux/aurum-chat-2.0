# WORK-004 — Organization, Identity, and Policy Foundation

## Objective

Create organization/tenant identity, people identity, roles, and explicit company policy foundations.

## Dependencies

WORK-003.

## Scope

- organizations;
- users;
- employees;
- authorization primitives;
- company configuration;
- explicit attention thresholds;
- action authority policy;
- approval policy.

## Acceptance Criteria

1. Tenant isolation is enforced.
2. Employees and users are distinct concepts.
3. Explicit company policies are persisted and versioned.
4. Policy evaluation is deterministic and independently testable.
5. Policy cannot be overridden by LLM/agent output.
