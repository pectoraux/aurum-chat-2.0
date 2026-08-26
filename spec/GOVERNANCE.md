# Aurum 2.0 Implementation Governance

## Roles

### Architect / Reviewer

Owns:

- architecture;
- ADRs;
- work decomposition;
- dependency ordering;
- acceptance criteria;
- architecture checks;
- adversarial review;
- architecture-change decisions;
- approval.

### z.ai Implementer

Owns:

- inspecting the actual repository;
- implementation;
- tests;
- migrations;
- required documentation;
- PRs;
- objective evidence.

z.ai does not own architecture.

## Mandatory Implementer Behavior

Before every WORK item:

1. Inspect actual repository state.
2. Read relevant frozen architecture/ADR/work item.
3. Verify dependencies are actually present.
4. Do not trust previous agent reports as evidence.
5. Implement only the requested scope.
6. Add/update tests.
7. Run architecture checks.
8. Run relevant regression tests.
9. Report exact commit/PR and evidence.

## AI/LLM Provider Hot-Swap Requirement

For every AI/LLM integration:

1. Domain code must call only the application-owned AI/LLM Gateway.
2. Provider/model SDKs are confined to provider adapters.
3. Provider/model names cannot become required semantic fields of domain entities.
4. A provider/model can be replaced without domain schema migration or business-logic rewrite.
5. Completed execution records must preserve provider/model metadata for auditability.
6. The same capability contract must be demonstrably executable against at least two provider/model implementations through tests or adapters.
7. Provider-specific prompt, response, tool, or embedding details must be normalized behind the gateway where they affect persistent cognition.
8. A model/provider outage may trigger policy-approved failover without changing domain semantics.

"Provider-neutral interface" is insufficient evidence. The implementation must demonstrate actual swapability.

## Architecture Change

If implementation discovers a genuine architectural conflict:

IMPLEMENTATION
→ ARCHITECTURE_CHANGE_REQUIRED
→ architect review
→ explicit change decision
→ architecture version update if accepted
→ revised work item(s)

Never silently alter a frozen primitive.

## Completion Standard

"Implemented" means:

- code exists;
- contracts are correct;
- tests pass;
- architecture checks pass;
- relevant integration/behavioral verification passes;
- no known scope violations remain;
- evidence is available.

Agent prose is not evidence.
