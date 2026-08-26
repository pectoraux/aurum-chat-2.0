# ADR-0017 — AI/LLM Provider and Model Hot-Swap

## Status

Accepted

## Decision

All AI/LLM capabilities are accessed through an application-owned, provider-independent gateway. Provider and model selection is runtime/configuration state, not a business-domain semantic dependency.

Aurum must be able to replace the provider and/or model used for a capability without changing domain code, business entities, persisted semantic state, or workflow definitions.

Provider/model identifiers may be retained in execution records for auditability, observability, cost accounting, and historical analysis, but they must not be required to interpret authoritative business/domain state.

Provider/model selection must distinguish capability, eligibility, policy, availability, performance, and preference.

## Rationale

AI providers and models will change frequently. Architectural coupling to a provider, model family, or model version would make normal model/provider replacement an architectural migration and would create unnecessary lock-in.

Aurum also needs to be able to compare, route, fail over, or replace models while preserving organizational memory and business state.

## Consequences

- Domain modules depend only on provider-independent AI capability contracts.
- Provider-specific adapters remain private to the LLM gateway.
- Persisted semantic/domain records remain readable after provider/model changes.
- Existing execution history records the provider/model actually used without making it a semantic dependency.
- A provider/model hot-swap test is mandatory verification for the gateway.
- Provider-specific hidden state cannot be the authoritative representation of organizational knowledge.

## Rejected Alternatives

### Direct provider integration from domain modules

Rejected because it creates provider lock-in and makes replacement invasive.

### Persisting provider/model identity as domain meaning

Rejected because provider/model identity describes implementation/execution, not organizational truth.

### Single fixed model for the lifetime of Aurum

Rejected because it prevents capability evolution, competitive evaluation, failover, and cost/performance optimization.
