# WORK-008 — Temporal World State

## Objective

Add temporal validity to mutable world relationships/state.

## Dependencies

WORK-007.

## Acceptance Criteria

1. Historical state remains queryable.
2. Current state can be resolved deterministically.
3. State changes preserve prior versions.
4. Temporal overlap/conflict rules are explicit and tested.
5. No update destroys historical truth.
