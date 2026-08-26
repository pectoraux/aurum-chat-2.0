# WORK-026 — Software Builder Lifecycle

## Objective

Implement the workflow for designing, building, verifying, deploying, and rolling back arbitrary software extensions.

## Dependencies

WORK-025, WORK-023, WORK-034, WORK-035.

## Acceptance Criteria

1. Automation/software opportunities can enter a build proposal.
2. Build proposals carry expected outcome, scope, architecture constraints, and required permissions.
3. Builder execution uses an isolated Agent Gateway execution.
4. Builder output is instantiated through the general-purpose Extension Runtime.
5. Verification is required before deployment.
6. Deployment requires configured authorization.
7. Failed extensions can be rolled back or disabled.
8. Extension/provider-specific implementation details remain behind module contracts.
9. Builder execution and resulting extension lifecycle are auditable.
10. A fixture demonstrates a real stateful extension being built, verified, installed, invoked, and rolled back.
