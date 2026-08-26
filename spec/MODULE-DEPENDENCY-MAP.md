# Aurum 2.0 — Module Dependency Map

## Rules

- Dependencies point toward lower-level/domain contracts.
- A module may consume another module's public contract but never its internals.
- Infrastructure adapters are reached through interfaces.
- LLM/AI providers are only reachable through the LLM Gateway.
- Agent providers/runtimes are only reachable through the Agent Gateway.
- Source connectors are only reachable through the Sources module.
- Action execution is policy-controlled.
- No module may treat LLM output as authoritative fact without domain validation.

## Layer 0 — Foundation

- `auth`
- `organizations`
- `audit`
- `events`

## Layer 1 — Reality and Memory

- `people`
- `world`
- `observations`
- `sources`
- `memory`

## Layer 2 — Epistemics and Cognition

- `epistemics`
- `goals`
- `attention`
- `investigation`
- `cognition`

## Layer 3 — Organizational Intelligence

- `environment`
- `presence`
- `processes`
- `capabilities`
- `workforce`
- `suppliers`

## Layer 4 — Action Workforce

- `actions`
- `agents`
- `extensions`

## Layer 5 — Learning

- `learning`

## Layer 6 — Human Interaction

- `conversations`
- `channels`
- `notifications`

## Provider Boundaries

- `llm` owns the provider-independent AI/LLM gateway and provider adapters.
- `agents` owns the provider-independent Agent Gateway and agent provider/runtime adapters.
- `sources` owns provider-independent source/connector contracts and connector adapters.
- `channels` owns provider-independent communication-channel contracts and channel adapters.

## Canonical Dependency Direction

```text
FOUNDATION
   ↓
REALITY / SOURCES / MEMORY
   ↓
EPISTEMICS / GOALS / COGNITION
   ↓
ORGANIZATIONAL INTELLIGENCE
   ↓
ACTION WORKFORCE
   ↓
LEARNING
   ↓
EXPERIENCE
```

The `llm` provider boundary may be consumed by `cognition` and other application modules only through its public gateway contract.

The `agents` module may consume the `llm` public capability contract where an agent runtime requires LLM reasoning, but provider adapters remain private.

The `sources` module may emit events/observations through public contracts; it must not own semantic world-model interpretation.

## Forbidden Dependencies

- Domain modules importing provider SDKs directly.
- Domain modules importing another module's database implementation.
- LLM provider code importing business-domain internals.
- Agent provider/runtime code importing business-domain internals.
- Source connector code leaking provider-specific types into domain contracts.
- Agents directly mutating authoritative workflow/domain state without an action contract.
- UI importing repositories or persistence internals.
- Redis used as the source of domain truth.
- Persisted domain entities containing required provider/model identifiers as semantic business dependencies.
