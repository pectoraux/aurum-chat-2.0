# WORK-029 — Channel Adapters

## Objective

Implement external communication channel adapters behind application-owned interfaces.

## Dependencies

WORK-028.

## Scope

Initial adapters may include WhatsApp-like chat, web chat, and voice/telephony where configured.

## Acceptance Criteria

1. Providers are hidden behind interfaces.
2. Incoming messages enter the observation pipeline.
3. Outgoing messages pass through action/communication policy.
4. Provider failures do not corrupt authoritative conversation state.
5. Message provenance is retained.
