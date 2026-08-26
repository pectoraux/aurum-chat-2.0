# Aurum 2.0 Architecture

This directory contains the frozen architectural specification and implementation-control artifacts for Aurum 2.0.

Aurum is an always-on organizational intelligence employee responsible for maintaining situational awareness of a company and its environment, understanding what is known and unknown, investigating consequential uncertainty, learning what is useful to the specific company, and recommending or executing authorized actions.

## Governance

- **Architect / Reviewer:** independent architecture owner
- **Implementer:** z.ai
- **Repository:** `pectoraux/aurum-chat-2.0`
- **Reference implementation:** Aurum 1.x may be consulted for lessons, but is not an architectural dependency.
- **Workflow:** implementation is performed through bounded WORK items with objective verification and independent architectural review.

## Authoritative documents

1. `ARCHITECTURE.md` — frozen system architecture
2. `ARCHITECTURE-LOCK.md` — non-negotiable invariants
3. `MODULE-DEPENDENCY-MAP.md` — ownership and dependency boundaries
4. `WORK-ITEM-DEPENDENCY-GRAPH.md` — initial implementation sequence
5. `ADR/` — architecture decision records
6. `work-items/` — initial implementation work orders

Do not silently redesign frozen architecture during implementation. Genuine architectural problems require an explicit architecture-change process.
