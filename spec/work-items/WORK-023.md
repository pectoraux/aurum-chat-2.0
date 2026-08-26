# WORK-023 — Agent Workforce

## Objective

Implement persistent specialist agents as organizational actors.

## Dependencies

WORK-022, WORK-019, WORK-034.

## Acceptance Criteria

1. Agent lifecycle is explicit.
2. Contracts/objectives/permissions/budgets are represented.
3. Recruitment proposals can require MD approval.
4. Agent execution is traceable through the Agent Gateway.
5. Agent state is authoritative outside the LLM.
6. Agent runtime/provider identity is not a semantic dependency of the Agent Workforce domain model.
7. Agent replacement can occur without rewriting workforce history.
