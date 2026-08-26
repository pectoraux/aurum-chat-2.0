# Aurum 2.0 — Architecture Lock

**Lock Version:** 1.0

This document is the concise non-negotiable contract for implementation.

## Core

1. Aurum is an organizational intelligence employee, not a chatbot product.
2. The world model includes both company and external environment.
3. Chat is a channel, not the system center.
4. Perception and action are subordinate to cognition and policy.

## Epistemics

5. Events and observations are immutable.
6. Claims, beliefs, and hypotheses are distinct.
7. Unknown is first-class.
8. Contradictions are preserved.
9. Beliefs are versioned.
10. Consequential beliefs have provenance.
11. LLM output is never authoritative merely because an LLM generated it.
12. Reality is immutable; understanding is mutable.

## Time

13. Mutable world relationships support temporal validity.
14. Historical understanding is retained.
15. Changes in belief must be explainable through evidence.

## Attention and Learning

16. Explicit company policy defines authority and thresholds.
17. Learned preferences cannot silently override explicit policy.
18. Learning is versioned and auditable.
19. Outcomes feed back into company-specific learning.

## Investigation

20. Aurum explicitly represents consequential unknowns.
21. Investigation is selected by expected information value and cost.
22. Aurum can investigate through systems, people, external sources, analysis, agents, or software.

## Organization

23. Company capabilities are represented independently of job titles.
24. People, agents, software, suppliers, and partners can provide capabilities.
25. Processes are inferred from observed work.

## Human Impact

26. Employment-impacting outputs are recommendations, not autonomous employment decisions.
27. Absence/presence is an inference and must retain uncertainty.
28. High-impact recommendations expose evidence, uncertainty, and alternatives.

## Agents

29. Agents have lifecycle, permissions, contracts, objectives, and performance.
30. Agent recruitment and termination follow policy/approval.
31. Agent state is authoritative outside the LLM.
32. Agents cannot bypass action policy.

## Software

33. Aurum may acquire arbitrary software capabilities through extensions.
34. Extensions have verification and lifecycle management.
35. Software deployment is policy-controlled.

## Modularity

36. Modules own domains.
37. Modules expose contracts.
38. Internal implementation is private.
39. Cross-module internal imports are forbidden.
40. Providers are hidden behind gateways.

## Infrastructure

41. PostgreSQL is authoritative domain/application state.
42. Redis is not domain truth.
43. Long-running work is asynchronous.
44. Executions are traceable.
45. Actions are idempotent where applicable.

## Governance

46. Frozen architecture cannot be silently changed during implementation.
47. Genuine architectural changes require an explicit change request.
48. z.ai implements work orders; it does not redefine architecture.
49. Completion claims require objective evidence.
50. Architectural approval requires review of the actual repository and verification evidence.
