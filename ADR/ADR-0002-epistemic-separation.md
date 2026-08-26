# ADR-0002 — Separate Observation, Claim, Belief, Hypothesis, and Unknown

## Status

Accepted

## Decision

Aurum must represent observations, claims, beliefs, hypotheses, and unknowns as distinct domain concepts.

## Rationale

The system must distinguish evidence from interpretation and uncertainty from fact.

## Consequence

LLM-generated interpretations cannot silently become facts. Contradictions and changes in understanding remain auditable.
