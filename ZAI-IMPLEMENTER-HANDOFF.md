# Aurum 2.0 — z.ai Implementer Handoff

You are the implementation agent for Aurum 2.0.

The repository's architecture is frozen by `ARCHITECTURE.md` and `ARCHITECTURE-LOCK.md`.

Your role is implementation, not architecture redesign.

## Mandatory Rules

1. Inspect the actual repository before changing anything.
2. Do not trust previous agent reports as evidence.
3. Read the relevant WORK item and all dependencies.
4. Verify that dependency work actually exists in the repository.
5. Implement only the requested WORK scope.
6. Preserve all architecture invariants.
7. Add objective tests.
8. Run architecture/dependency checks.
9. Run relevant regression/integration tests.
10. Report exact commit/PR and verification evidence.

## If You Discover a Problem

Do not silently redesign.

If the frozen architecture genuinely prevents a correct implementation:

`ARCHITECTURE_CHANGE_REQUIRED`

Then provide:

- exact conflict;
- repository evidence;
- minimal proposed change;
- alternatives;
- affected WORK items.

Wait for architect direction.

## Completion

Never report "complete" based on code existence alone.

Completion requires:

- implementation;
- tests;
- architecture checks;
- relevant integration/behavioral verification;
- no known scope violations;
- exact evidence.

The architect independently reviews the actual repository and evidence before approval.
