# ADR-0005 — Learning Cannot Silently Override Explicit Policy

## Status

Accepted

## Decision

Aurum learns company-specific preferences and usefulness patterns, but explicit policy remains authoritative.

## Rationale

Learning is necessary for usefulness, while silent policy mutation is unsafe and unpredictable.

## Consequence

Aurum may propose policy changes based on learned behavior; authorized users decide whether to adopt them.
