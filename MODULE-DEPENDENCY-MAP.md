# Aurum 2.0 — Module Dependency Map

## Rules

- Dependencies point toward lower-level/domain contracts.
- A module may consume another module's public contract but never its internals.
- Infrastructure adapters are reached through interfaces.
- LLM providers are only reachable through the LLM gateway.
- Action execution is policy-controlled.
- No module may treat LLM output as authoritative fact without domain validation.

## Layers

### Layer 0 — Foundation

- `auth`
- `organizations`
- `audit`
- `events`

### Layer 1 — Reality and Memory

- `people`
- `world`
- `observations`
- `memory`

### Layer 2 — Epistemics

- `epistemics`
- `attention`
- `investigation`

### Layer 3 — Organizational Intelligence

- `environment`
- `presence`
- `processes`
- `capabilities`
- `workforce`
- `suppliers`

### Layer 4 — Action Workforce

- `agents`
- `extensions`
- `actions`

### Layer 5 — Learning

- `learning`

### Layer 6 — Human Interaction

- `conversations`
- `channels`
- `notifications`

### Provider Boundary

- `llm`

## Canonical Dependency Direction

```text
FOUNDATION
   ↓
REALITY / MEMORY
   ↓
EPISTEMICS
   ↓
ORGANIZATIONAL INTELLIGENCE
   ↓
ACTION WORKFORCE
   ↓
LEARNING
   ↓
EXPERIENCE
```

Cross-cutting `audit` and authorization contracts may be consumed by all modules through public interfaces.

## Forbidden Dependencies

- Domain modules importing provider SDKs directly.
- Domain modules importing another module's database implementation.
- LLM provider code importing business-domain internals.
- Agents directly mutating authoritative workflow state without an action contract.
- UI importing repositories or persistence internals.
- Redis used as the source of domain truth.
