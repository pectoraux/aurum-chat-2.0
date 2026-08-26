# WORK-017 — Presence and Activity Inference

## Objective

Create authorized presence/activity inference.

## Dependencies

WORK-016, WORK-008.

## Acceptance Criteria

1. Authorized signals can be ingested.
2. Expected presence and observed presence are distinct.
3. Absence is represented as an inference/unknown.
4. Confidence and provenance are retained.
5. The system cannot turn missing telemetry directly into an adverse employee fact.
