# Aurum 2.0 — Architecture Lock

**Lock Version:** 1.1

This document is the concise non-negotiable contract for implementation.

## Core

1. Aurum is an organizational intelligence employee, not a chatbot product.
2. The world model includes both company and external environment.
3. Chat is a channel, not the system center.
4. Perception and action are subordinate to cognition and policy.
5. Goals/desired states are first-class and distinct from beliefs and attention policy.

## Epistemics

6. Events and observations are immutable.
7. Claims, beliefs, and hypotheses are distinct.
8. Unknown is first-class.
9. Contradictions are preserved.
10. Beliefs are versioned.
11. Consequential beliefs have provenance.
12. LLM output is never authoritative merely because an LLM generated it.
13. Reality is immutable; understanding is mutable.

## Time

14. Mutable world relationships support temporal validity.
15. Historical understanding is retained.
16. Changes in belief must be explainable through evidence.

## Attention and Learning

17. Explicit company policy defines authority and thresholds.
18. Learned preferences cannot silently override explicit policy.
19. Learning is versioned and auditable.
20. Outcomes feed back into company-specific learning.

## Investigation and Cognition

21. Aurum explicitly represents consequential unknowns.
22. Investigation is selected by expected information value and cost.
23. A dedicated cognitive orchestration layer connects perception, memory, epistemics, attention, investigation, learning, and action.
24. LLM calls do not own cognitive workflow state.

## Organization

25. Company capabilities are represented independently of job titles.
26. People, agents, software, suppliers, and partners can provide capabilities.
27. Processes are inferred from observed work.

## Human Impact

28. Employment-impacting outputs are recommendations, not autonomous employment decisions.
29. Presence/absence is an inference and must retain uncertainty.
30. High-impact recommendations expose evidence, uncertainty, and alternatives.

## Agents

31. Agents have lifecycle, permissions, contracts, objectives, and performance.
32. Agent recruitment and termination follow policy/approval.
33. Agent state is authoritative outside the LLM.
34. Agent execution occurs behind a provider-independent Agent Gateway.
35. Agents cannot bypass action policy.

## Software

36. Aurum may acquire arbitrary software capabilities through extensions.
37. The extension runtime must support persistent state, UI, schedules, events, scoped external access, isolation, quotas, lifecycle, deployment, rollback, and auditing.
38. Extensions remain constrained by security/policy boundaries, not by a fixed product-feature catalog.
39. Software deployment is policy-controlled.

## Sources

40. All connectors are behind application-owned provider-independent interfaces.
41. Ingestion supports provenance, deduplication, retry, checkpointing, and replay/reprocessing.
42. Connector/provider-specific objects may not leak into domain modules.

## AI/LLM Provider Independence

43. All AI/LLM capabilities are accessed through the provider-independent LLM Gateway.
44. No business/domain state may require a specific provider, model family, or model version.
45. Providers/models are hot-swappable without domain migration.
46. Existing authoritative data must remain readable when a provider/model changes.
47. Completed executions retain provider/model metadata for auditability only.
48. Provider/model selection distinguishes capability, eligibility, policy, performance, availability, and preference.
49. No provider is architecturally privileged.

## Modularity

50. Modules own domains.
51. Modules expose contracts.
52. Internal implementation is private.
53. Cross-module internal imports are forbidden.
54. Providers are hidden behind gateways.

## Infrastructure

55. PostgreSQL is authoritative domain/application state.
56. Redis is not domain truth.
57. Long-running work is asynchronous.
58. Executions are traceable.
59. Actions are idempotent where applicable.
60. Notifications are delivery infrastructure, not authoritative domain state.
61. Audit records are append-only from the domain perspective.

## Governance

62. Frozen architecture cannot be silently changed during implementation.
63. Genuine architectural changes require an explicit change request.
64. z.ai implements work orders; it does not redefine architecture.
65. Completion claims require objective evidence.
66. Architectural approval requires review of the actual repository and verification evidence.
