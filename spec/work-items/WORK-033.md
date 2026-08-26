# WORK-033 — Cognitive Orchestration

## Objective

Implement the deterministic orchestration layer that connects perception, memory, epistemics, goals, attention, investigation, learning, and action.

## Dependencies

WORK-009, WORK-010, WORK-011, WORK-012, WORK-031, WORK-036.

## Canonical Loop

new observation
→ update evidence/memory
→ update world model
→ evaluate claims/beliefs
→ detect contradictions/unknowns/changes
→ evaluate goals and attention
→ choose investigation when useful
→ execute investigation
→ update model
→ recommend / ask / propose / act according to policy
→ record outcome
→ learn

## Acceptance Criteria

1. Cognition is represented as explicit executions with traceable inputs/outputs.
2. LLM reasoning is invoked only through the AI/LLM Gateway.
3. Cognitive orchestration owns sequencing but not domain truth.
4. Policy/authorization gates are deterministic and cannot be bypassed by LLM output.
5. Goals and desired states can materially influence attention/investigation evaluation through their provider-independent contracts.
6. A consequential unknown can trigger a bounded investigation.
7. Investigation results feed back into evidence/world state.
8. Attention decisions can result in no notification, a question, a recommendation, or an authorized action.
9. Cognitive executions are asynchronous and resumable.
10. Duplicate events cannot create duplicate authoritative actions.
11. A complete end-to-end fixture proves observation → cognition → goal/attention evaluation → investigation → updated belief → attention decision.
