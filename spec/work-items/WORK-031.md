# WORK-031 — AI/LLM Gateway and Hot-Swappable Provider Registry

## Objective

Implement the provider-independent AI/LLM Gateway so any eligible AI/LLM provider or model can be swapped without domain-code or domain-state migration.

## Dependencies

WORK-003, WORK-004, WORK-002.

## Scope

- provider-independent capability interfaces;
- provider/model registry;
- runtime capability metadata;
- provider/model eligibility;
- policy/preferences;
- health/availability;
- routing/selection;
- request normalization;
- response normalization;
- structured outputs;
- retries/failover;
- usage/cost recording;
- provider/model execution metadata;
- provider-specific adapters behind private boundaries.

## Acceptance Criteria

1. Domain modules can request AI capabilities without importing a provider SDK.
2. Multiple providers/models can be registered behind the same gateway contract.
3. Provider/model can be changed through configuration/selection without changing domain code.
4. Existing authoritative domain records remain valid/readable after provider/model replacement.
5. Completed executions retain provider/model metadata for auditability.
6. Capability, eligibility, availability, policy, performance, and preference are separate concerns.
7. No provider is architecturally privileged.
8. A provider failure can fail over according to policy without leaking provider-specific semantics.
9. Structured-output contracts remain provider-independent.
10. Architecture checks reject direct provider imports from domain modules.

## Explicit Hot-Swap Test

A test must run the same domain capability once through provider A and then provider B using the same provider-independent contract and prove no domain migration or semantic schema change is required.

## Out of Scope

- business-domain cognition;
- conversation UI;
- agent workforce lifecycle;
- source connectors.
