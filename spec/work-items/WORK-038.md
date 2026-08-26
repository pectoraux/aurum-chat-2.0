# WORK-038 — Notification Delivery

## Objective

Implement policy-controlled proactive notification and escalation delivery.

## Dependencies

WORK-012, WORK-022, WORK-028.

## Scope

- notification records;
- channel routing;
- interruption/digest modes;
- escalation;
- retry;
- deduplication;
- acknowledgement;
- suppression;
- delivery audit.

## Acceptance Criteria

1. Attention items can produce notifications according to policy.
2. Notifications can be routed to configured channels without provider-specific types leaking into domain modules.
3. Duplicate notification attempts do not create duplicate authoritative delivery records.
4. Failed delivery retries safely.
5. Users can acknowledge/suppress notifications according to policy.
6. Notification state is auditable but is not authoritative business/domain truth.
7. Urgent and non-urgent delivery modes are distinguishable.
