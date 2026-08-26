# Aurum 2.0 — Initial Work Item Dependency Graph

The implementation plan is a dependency DAG. Work is eligible when its actual dependencies are verified complete; it is not required to follow one artificial serial chain.

```text
FOUNDATION
WORK-001
  ↓
WORK-002
  ↓
WORK-003
  ↓
WORK-004
  ├──────────────→ WORK-012 Attention Policy
  ├──────────────→ WORK-036 Goals / Desired State
  └──────────────→ WORK-031 AI/LLM Gateway

WORK-005 Events
  ├──────────────→ WORK-006 Observations + Provenance
  └──────────────→ WORK-032 Sources / Connectors

WORK-006
  ↓
WORK-007 World Entities / Relationships
  ↓
WORK-008 Temporal World State
  ↓
WORK-009 Claims / Evidence / Beliefs
  ├──────────────→ WORK-010 Contradiction / Epistemics
  └──────────────→ WORK-036 Goals / Desired State

WORK-010
  ↓
WORK-011 Unknowns / Investigation Contracts

WORK-012 + WORK-031 + WORK-009 + WORK-010 + WORK-011 + WORK-036
  ↓
WORK-033 Cognitive Orchestration

WORK-012 + WORK-013 + WORK-027 + WORK-033
  ↓
WORK-028 Conversation Domain

SOURCE / ENVIRONMENT TRACK
WORK-032
  ↓
WORK-014 Environmental Intelligence
  ↓
WORK-015 Change Detection / Impact Analysis

PEOPLE / ORGANIZATION TRACK
WORK-009 + WORK-008
  ↓
WORK-016 Organizational Knowledge / Transactive Memory
  ├──────────────→ WORK-017 Presence / Activity
  ├──────────────→ WORK-018 Process Reconstruction
  └──────────────→ WORK-019 Capability Graph

WORK-019
  ├──────────────→ WORK-020 Workforce Intelligence
  └──────────────→ WORK-021 Supplier Intelligence

ACTION TRACK
WORK-022 Action Policy
  ├──────────────→ WORK-023 Agent Workforce
  ├──────────────→ WORK-025 Extension Contracts
  └──────────────→ WORK-038 Notifications

WORK-031 + WORK-002 + WORK-022
  ↓
WORK-034 Agent Gateway / Runtime
  ↓
WORK-023 Agent Workforce
  ↓
WORK-024 Agent Evaluation / Termination

EXTENSION TRACK
WORK-025 + WORK-022
  ↓
WORK-035 General-Purpose Extension Runtime

WORK-023 + WORK-034 + WORK-035 + WORK-025
  ↓
WORK-026 Software Builder Lifecycle

OUTCOME / LEARNING TRACK
WORK-013 + WORK-021 + WORK-023 + WORK-026
  ↓
WORK-027 Outcome Measurement
  ↓
WORK-013 remains the learning-model contract; outcome evidence continuously feeds it.

AUDIT TRACK
WORK-005 + WORK-006 + WORK-011 + WORK-022 + WORK-031
  ↓
WORK-037 Audit / Decision Evidence

NOTIFICATION / EXPERIENCE TRACK
WORK-012 + WORK-022 + WORK-028
  ↓
WORK-038 Notification Delivery
  ↓
WORK-030 MD Control Surface

FINAL EXPERIENCE
WORK-022 + WORK-027 + WORK-028 + WORK-036 + WORK-037 + WORK-038
  ↓
WORK-030 MD Control Surface

CHANNEL TRACK
WORK-028
  ↓
WORK-029 Channel Adapters

The channel adapter layer may be implemented in parallel with notification delivery after the conversation contract exists, but both must obey the same provider-isolation and action-policy rules.
```

## Parallelization Rules

Once foundation contracts are stable, independent branches may be implemented in parallel only when:

1. all declared dependencies are actually present in the repository;
2. no two work items are simultaneously modifying the same architectural primitive;
3. no work item depends on an unverified contract;
4. architecture checks remain green.

Likely parallel tracks include:

- environmental intelligence;
- people/presence;
- process intelligence;
- capability/workforce;
- LLM gateway;
- source connectors.

## Critical Rule

Every WORK item requires:

- explicit acceptance criteria;
- objective verification;
- architecture checks;
- relevant integration/behavioral tests;
- exact scope and out-of-scope definition;
- architect review of the actual repository.

Do not collapse the graph into a single milestone.
