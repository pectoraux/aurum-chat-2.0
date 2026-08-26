# WORK-006 — Observation and Provenance Foundation

## Objective

Create the evidence ingestion primitive.

## Dependencies

WORK-005.

## Scope

Implement observations, provenance, source identity, artifact references, extraction lineage, confidence, and source reliability interfaces.

## Acceptance Criteria

1. An observation can reference its source and original artifact.
2. Observation history is immutable.
3. Extraction lineage is preserved.
4. Observation metadata is distinguishable from interpreted claims.
5. No LLM result can bypass observation/evidence semantics.
