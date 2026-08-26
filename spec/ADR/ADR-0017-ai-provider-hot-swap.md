# ADR-0017 — AI/LLM Provider and Model Hot-Swap

## Status

Accepted

## Decision

All AI/LLM capabilities are accessed through the application-owned LLM Gateway.

The provider/model implementation used for a capability must be replaceable without:

- changing domain code;
- changing semantic business entities;
- migrating authoritative domain state;
- changing workflow definitions.

Provider/model identity is execution metadata for auditability, not a semantic business dependency.

## Runtime Behavior

The gateway maintains a provider/model registry and selects an eligible implementation based on:

- requested capability;
- authorization/subscription;
- company/project policy;
- availability/health;
- performance evidence;
- configured preference;
- cost/latency constraints where applicable.

Future executions use the current selection. Completed executions retain the provider/model metadata that was actually used.

## Required Verification

The implementation must execute the same provider-independent capability through at least two provider/model implementations and prove that switching between them requires no domain migration or business-logic rewrite.

## Rationale

Aurum must remain free to change AI providers and models as capability, cost, latency, availability, safety, pricing, or strategic requirements change. AI providers are implementation dependencies, not architectural primitives.
