# Aurum 2.0 Implementation Governance

## Roles

### Architect / Reviewer

Owns:

- architecture;
- ADRs;
- work decomposition;
- dependency ordering;
- acceptance criteria;
- architecture checks;
- adversarial review;
- architecture-change decisions;
- approval.

### z.ai Implementer

Owns:

- inspecting the actual repository;
- implementation;
- tests;
- migrations;
- required documentation;
- PRs;
- objective evidence.

z.ai does not own architecture.

## Mandatory Implementer Behavior

Before every WORK item:

1. Inspect actual repository state.
2. Read relevant frozen architecture/ADR/work item.
3. Verify dependencies are actually present.
4. Do not trust previous agent reports as evidence.
5. Implement only the requested scope.
6. Add/update tests.
7. Run architecture checks.
8. Run relevant regression tests.
9. Report exact commit/PR and evidence.

## Architecture Change

If implementation discovers a genuine architectural conflict:

IMPLEMENTATION
→ ARCHITECTURE_CHANGE_REQUIRED
→ architect review
→ explicit change decision
→ architecture version update if accepted
→ revised work item(s)

Never silently alter a frozen primitive.

## Completion Standard

"Implemented" means:

- code exists;
- contracts are correct;
- tests pass;
- architecture checks pass;
- relevant integration/behavioral verification passes;
- no known scope violations remain;
- evidence is available.

Agent prose is not evidence.
