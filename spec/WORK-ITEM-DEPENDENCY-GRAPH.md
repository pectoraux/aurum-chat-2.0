# Aurum 2.0 — Initial Work Item Dependency Graph

The graph is intentionally conservative. Each work item should remain small enough for independent repository verification.

```text
WORK-001 Architecture / repository foundation
   ↓
WORK-002 Infrastructure foundation
   ↓
WORK-003 Module contract and architecture enforcement
   ↓
WORK-004 Organization / tenant / identity foundation
   ↓
WORK-005 Event foundation
   ↓
WORK-006 Observation + provenance foundation
   ↓
WORK-007 World entities + relationships
   ↓
WORK-008 Temporal world state
   ↓
WORK-009 Claims / evidence / belief model
   ↓
WORK-010 Contradiction + epistemic evaluation
   ↓
WORK-011 Unknowns + investigation contracts
   ↓
WORK-012 Attention policy
   ↓
WORK-013 Company learning model
   ↓
WORK-014 External/environment ingestion
   ↓
WORK-015 Change detection + impact analysis
   ↓
WORK-016 People / organizational knowledge
   ↓
WORK-017 Presence / activity inference
   ↓
WORK-018 Process reconstruction
   ↓
WORK-019 Capability graph
   ↓
WORK-020 Workforce intelligence
   ↓
WORK-021 Supplier intelligence
   ↓
WORK-022 Action policy
   ↓
WORK-023 Agent workforce
   ↓
WORK-024 Agent evaluation / termination
   ↓
WORK-025 Extension contracts
   ↓
WORK-026 Software builder lifecycle
   ↓
WORK-027 Outcome measurement
   ↓
WORK-028 Conversation domain
   ↓
WORK-029 Channel adapters
   ↓
WORK-030 MD control surface
```

### Parallelization

After the foundation and contracts are stable, independent work may be parallelized only where the dependency graph proves no shared mutable architectural state.

Examples of potentially parallel tracks:

- external/environment ingestion
- presence
- process intelligence
- capability graph

But architecture-changing discoveries must return to the architect before implementation continues.

## Rule

Do not collapse the entire graph into a single milestone. Each WORK item requires its own acceptance criteria, tests, architecture checks, and review.
