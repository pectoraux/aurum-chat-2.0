# WORK-022 — Action Policy

## Objective

Implement the policy-controlled action authorization boundary.

## Dependencies

WORK-012, WORK-020.

## Acceptance Criteria

1. Actions are classified by authority level.
2. Approval requirements are deterministic.
3. Agents/LLMs cannot bypass authorization.
4. Every executed action is auditable.
5. Denied actions cannot be executed through alternate paths.
