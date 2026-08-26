# WORK-001 — Repository and Architecture Foundation

## Objective

Create the Aurum 2.0 repository foundation and make the frozen architecture enforceable before domain implementation begins.

## Dependencies

None.

## Scope

- initialize repository;
- establish project/toolchain structure;
- install test infrastructure;
- add architecture documentation;
- add architecture lock;
- establish module boundary enforcement;
- establish baseline CI;
- establish environment/configuration conventions;
- establish authoritative database/infrastructure interfaces without implementing business domains.

## Acceptance Criteria

1. Repository builds.
2. Baseline tests pass.
3. Architecture documents are present.
4. Architecture lock is referenced by implementation governance.
5. Module-boundary checks exist and can fail the build.
6. Provider SDKs cannot be imported directly by domain modules.
7. Infrastructure access is behind application-owned interfaces.
8. PostgreSQL is designated authoritative state.
9. Redis is not treated as domain truth.
10. CI runs formatting, type/static checks, tests, and architecture checks.

## Out of Scope

- world model implementation;
- chat UI;
- agents;
- connectors;
- LLM business logic.

## Required Evidence

- exact commit;
- test output;
- architecture-check output;
- CI configuration;
- dependency/boundary check output.

## Review Rule

The architect reviews the actual repository, not the implementer's narrative.
