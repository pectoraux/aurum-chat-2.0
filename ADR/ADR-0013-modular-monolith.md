# ADR-0013 — Modular Monolith First

## Status

Accepted

## Decision

Aurum begins as a modular monolith with explicit domain boundaries.

## Rationale

The product's early risk is conceptual and behavioral correctness, not distributed-systems scale. Strong boundaries can be enforced without premature service decomposition.

## Consequence

Each module has public contracts and private implementation. Extraction into services remains possible later without requiring domain redesign.
