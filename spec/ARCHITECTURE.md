# Aurum 2.0 — Frozen Architecture Specification

**Status:** FROZEN
**Version:** 1.0
**Repository:** `pectoraux/aurum-chat-2.0`

## 1. Product Definition

Aurum is an always-on organizational intelligence employee.

Its responsibility is to maintain situational awareness of:

- the company;
- its people;
- internal operations;
- the external environment;
- organizational capabilities;
- changes affecting company objectives;
- consequential uncertainties.

Its core loop is:

**observe → remember → understand → evaluate → investigate → learn → recommend → act when authorized**

Conversation is a channel, not the architectural center.

## 2. Fundamental Model

The fundamental object is:

**Company + Environment + their relationships + desired state + organizational capability + time.**

Aurum therefore maintains one evolving world model containing both internal and external reality.

## 3. Major Architectural Layers

1. Experience / Channels
2. Human Interaction
3. Organizational Cognition
4. World Model
5. Memory / Epistemics
6. Perception
7. Action

Perception and action are below cognition. Incoming information does not directly become an action.

## 4. World Model

### Entities

The extensible ontology includes, among others:

- Person
- Employee
- Team
- Customer
- Supplier
- Subcontractor
- Competitor
- Regulator
- Government body
- Product
- Service
- Asset
- Location
- Construction site
- Project
- Process
- Contract
- Market
- Industry
- Technology
- Agent
- Software extension
- Organizational capability
- Goal
- Risk
- Opportunity

The ontology must remain extensible. Do not freeze an unnecessarily huge taxonomy.

### Events

Events represent things that happened or are reported to have happened.

Events are immutable historical records.

### Observations

Observations record what Aurum encountered, including provenance, source, channel, timestamp, extraction lineage, permissions, and confidence.

An observation is evidence, not automatically truth.

### Claims

Claims are semantic propositions derived from observations or other evidence.

Claims may conflict.

### Beliefs

Beliefs represent Aurum's current working understanding. Beliefs are versioned and can change as evidence changes.

### Hypotheses

Hypotheses are possible explanations that have not been established as facts.

### Unknowns

Unknowns are first-class objects. A consequential unknown includes importance, decision impact, urgency, hypotheses, confidence, candidate evidence sources, estimated investigation cost, and a proposed investigation.

### Contradictions

Contradictory evidence is retained and surfaced for investigation. It must not be silently erased.

## 5. Temporal Model

Everything that can change must support temporal validity.

Aurum must be able to answer:

- What is true now?
- What was believed previously?
- When did our understanding change?
- What evidence changed it?
- Was a previous belief wrong or merely outdated?

**Reality is immutable. Understanding is mutable.**

Events and observations are immutable. Claims and beliefs are versioned. Workflow state is mutable and traceable.

## 6. Provenance

Every consequential claim and belief must be traceable to evidence:

belief → claim → evidence → observation → source → original artifact.

Aurum must be able to answer why it believes something and what evidence would change its mind.

## 7. Attention Model

The company explicitly configures:

- monitored domains;
- strategic priorities;
- thresholds;
- escalation policies;
- urgency;
- acceptable noise;
- critical entities;
- notification preferences;
- approval requirements.

Attention policy determines what deserves human attention. Information can be retained without interrupting people.

## 8. Goals and Desired State

Goals represent explicit desired organizational states and outcomes.

A goal may define:

- objective;
- target state;
- metric;
- threshold;
- horizon;
- owner;
- priority;
- evidence sources;
- success criteria.

Goals are distinct from beliefs and attention policies.

The system may detect gaps between observed state and desired state, but such gaps remain evidence-backed findings or hypotheses until evaluated.

## 9. Learned Company Model

Aurum learns what is useful to a particular company from:

- explicit feedback;
- behavioral feedback;
- outcomes;
- prediction accuracy;
- source reliability;
- investigation effectiveness;
- agent performance.

Learned preferences must never silently override explicit policy.

Aurum may propose policy changes, but the configured authority decides whether they become policy.

## 10. Environmental Intelligence

Aurum may continuously gather authorized external information from sources such as:

- news;
- government;
- regulation;
- economic indicators;
- industry publications;
- competitors;
- suppliers;
- customers;
- technology;
- labor markets;
- geography;
- weather/climate where relevant;
- other external sources.

External information follows:

external event → observation → claim → relationship to company → impact analysis → attention decision.

External and internal information use the same evidence/provenance semantics.

## 11. Source and Connector Architecture

Every external/internal information source is represented through a provider-independent source/connector boundary.

```text
Source definition
      ↓
Connector adapter
      ↓
Ingestion execution
      ↓
Raw artifact / event
      ↓
Observation + provenance
```

A source definition may include:

- source identity;
- source type;
- capabilities;
- authorization state;
- permissions/scope;
- sync mode;
- cursor/checkpoint;
- rate limits;
- reliability;
- tenant ownership.

Connector implementations are replaceable. They must not leak provider-specific objects into domain modules.

Connectors must support idempotent webhook and polling ingestion where applicable, deduplication, retry, checkpointing, and replay/reprocessing without corrupting authoritative history.

## 12. Presence and Activity Intelligence

Aurum may infer presence/activity from authorized signals such as:

- schedules;
- access systems;
- site check-ins;
- company devices;
- work applications;
- authorized location systems;
- meetings;
- calls;
- messages;
- task activity;
- supervisor reports.

Absence is an inference, not automatically a fact. Missing telemetry must not become an accusation.

## 13. Process Intelligence

Aurum reconstructs how work actually happens from events and observations.

It detects:

- repetitive work;
- unnecessary handoffs;
- duplicated entry;
- bottlenecks;
- manual effort;
- error-prone steps;
- unnecessary approvals;
- automation opportunities;
- software opportunities.

It can estimate frequency, labor cost, cycle time, error rate, affected employees, automation potential, and expected ROI.

## 14. Capability Graph

Capabilities may be possessed by:

- employees;
- teams;
- agents;
- software;
- suppliers;
- subcontractors;
- external partners.

The graph answers:

- What does the company need?
- What can it currently do?
- Who/what can do it?
- How well?
- What is missing?
- Can it be trained?
- Should it hire?
- Should it automate?
- Should it outsource?
- Should it recruit an agent?

## 15. Workforce Intelligence

Aurum may identify:

- skill gaps;
- training opportunities;
- workload imbalance;
- underutilization;
- recurring errors;
- process friction;
- capability mismatch;
- staffing requirements.

For employment-impacting decisions the flow is:

evidence → assessment → alternatives → recommendation → authorized human decision.

Aurum does not autonomously terminate employees.

## 16. Supplier and External Workforce Intelligence

Aurum may continuously evaluate suppliers/subcontractors across:

- price;
- quality;
- reliability;
- capacity;
- delivery;
- geography;
- financial risk;
- compliance;
- historical performance;
- relationship quality;
- alternatives;
- switching cost.

It may recommend supplier changes, diversification, renegotiation, or new partners.

## 17. Investigation Engine

Investigation is driven by expected information value.

For an unknown, Aurum evaluates:

- importance;
- potential decision impact;
- investigation cost;
- available sources;
- expected confidence gain;
- urgency.

Possible investigation actions include:

- search organizational memory;
- query connected systems;
- search external sources;
- ask employees;
- ask managers;
- inspect documents;
- run analyses;
- commission agents;
- build temporary analyses;
- execute authorized actions.

## 18. Cognitive Orchestration

A dedicated cognitive orchestrator connects perception, memory, world state, epistemics, investigation, attention, learning, and action.

Canonical loop:

```text
new observation
→ update evidence/memory
→ update world model
→ evaluate claims/beliefs
→ detect contradictions/unknowns/changes
→ evaluate attention and goals
→ choose investigation if useful
→ execute investigation
→ update model
→ recommend / ask / propose / act according to policy
→ record outcome
→ learn
```

No individual LLM call is the system's cognitive authority. Cognitive orchestration is deterministic at the workflow/policy level and may use LLMs for bounded reasoning tasks.

## 19. Transactive Organizational Memory

Aurum maintains knowledge of who:

- knows;
- owns;
- has experience with;
- possesses a capability;
- works on;
- decides;
- influences.

This lets Aurum investigate through the right people.

## 20. Agent Workforce

Agents are organizational actors, not merely LLM calls.

Lifecycle:

PROPOSED → APPROVAL → RECRUITED → ACTIVE → EVALUATED → RETAIN / MODIFY / TERMINATE.

Agents have:

- role;
- capabilities;
- permissions;
- contract;
- objectives;
- budget;
- expected outcomes;
- performance metrics;
- cost;
- owner;
- review schedule;
- activity history.

Aurum may recommend recruitment. Approval requirements are policy-controlled.

## 21. Agent Gateway and Runtime

Persistent agent definitions are separate from execution infrastructure.

```text
Agent definition
     ↓
Agent Gateway
     ↓
Provider/runtime adapter
     ↓
Agent execution
     ↓
Execution result + evidence + cost + outcome
```

Agent providers are replaceable. Agent business logic must not depend directly on a provider SDK.

Agent execution is asynchronous, traceable, permission-scoped, retryable, and idempotent where applicable.

## 22. Agent Termination

Aurum continuously evaluates agents for:

- poor outcomes;
- excessive cost;
- declining performance;
- duplicate capability;
- obsolete requirement;
- replacement;
- security concerns;
- insufficient utilization.

Termination follows policy and authorization, then:

approval → contract termination → permission revocation → runtime shutdown → knowledge retention → audit.

## 23. Extension / Software Builder

Aurum can identify opportunities for arbitrary software capabilities.

Lifecycle:

observed problem → process model → opportunity → software feasibility → design → approval → builder → verification → deployment → outcome observation.

The extension system must not be artificially constrained to a predefined list of feature types.

### Extension runtime capabilities

The runtime must be capable of hosting real applications, not only stateless functions. It must support, subject to declared manifest permissions:

- persistent scoped state;
- host-rendered/declarative UI surfaces;
- scheduled triggers;
- event subscriptions;
- scoped external participants/access;
- isolated execution;
- quotas and resource controls;
- versioned manifests and compatibility;
- deployment, rollback, disablement, and lifecycle state;
- auditable invocation and outcome measurement.

Arbitrary extension functionality remains constrained by the security sandbox, platform APIs, declared permissions, and policy. It must not be constrained to a fixed product-feature catalog.

## 24. Action Authority

Aurum distinguishes:

- OBSERVE
- ANALYZE
- RECOMMEND
- ASK
- PROPOSE
- EXECUTE

Company policy determines which require approval.

LLMs and agents cannot bypass action policy.

## 25. LLM and AI Provider Gateway

All AI/LLM capabilities are accessed through provider-independent application-owned interfaces.

```text
Cognitive capability
       ↓
AI/LLM Gateway
       ↓
Provider/model registry
       ↓
Provider adapter
       ↓
Selected model
```

The gateway owns:

- provider/model registry;
- capability metadata;
- availability and health;
- authorization/subscription checks;
- routing/selection;
- request normalization;
- response normalization;
- retries/failover;
- usage/cost recording;
- error semantics;
- model-specific adaptation.

### Hot-swappability invariant

Aurum must be able to switch the provider and/or model used for an AI capability without changing domain code, business entities, persisted semantic state, or workflow definitions.

A provider/model may be changed at runtime or configuration rollout time without an architectural migration. Existing executions retain their recorded provider/model metadata for auditability; future executions use the current eligible selection.

Domain state may reference provider-independent capability identifiers and execution records, but must never make a provider/model name a required semantic dependency.

Provider/model selection distinguishes:

- capability;
- eligibility;
- performance;
- policy;
- availability;
- user/company preference.

No provider is architecturally privileged.

## 26. AI/LLM State and Portability

Prompts, tool schemas, structured outputs, embeddings, and model-specific configuration must be versioned behind provider-independent contracts where they affect persistent cognition.

Persisted business meaning must not depend on opaque provider-specific hidden state.

Changing a provider/model may change future outputs, but it must not make existing authoritative domain data unreadable.

## 27. Learning

Learning incorporates:

- explicit feedback;
- behavioral feedback;
- outcome feedback;
- prediction feedback;
- source feedback;
- agent performance;
- investigation efficiency;
- provider/model performance where relevant.

Learned models are versioned and auditable.

## 28. Audit and Decision Evidence

Aurum maintains an authoritative audit record for consequential cognition and actions.

It must be possible to reconstruct:

- observed input;
- evidence used;
- belief/claim state;
- unknowns considered;
- policy evaluated;
- model/provider used;
- recommendation;
- approval;
- execution;
- result;
- outcome;
- subsequent learning.

Audit records are append-only from the domain perspective.

## 29. Notifications

Notifications are a dedicated policy-controlled delivery capability for:

- urgent interruptions;
- attention items;
- digests;
- escalations;
- approval requests;
- execution results.

Notification delivery is asynchronous, retryable, deduplicated, auditable, and subject to user/channel policy.

## 30. Conversation and Channels

Conversations are persistent interaction records, not authoritative organizational truth by themselves.

Incoming messages enter perception/evidence semantics. Outgoing messages are actions subject to communication policy.

Channels include provider-independent adapters for, where configured:

- WhatsApp-like messaging;
- web chat;
- voice/telephony;
- other approved channels.

## 31. Module Boundaries

Initial ownership modules:

- auth
- organizations
- people
- world
- events
- observations
- sources
- memory
- epistemics
- attention
- goals
- investigation
- cognition
- environment
- presence
- processes
- capabilities
- workforce
- suppliers
- agents
- extensions
- actions
- learning
- conversations
- channels
- notifications
- llm
- audit

Each module owns its domain and exposes public contracts. Internal implementation is private.

## 32. Infrastructure

Initial deployment is a modular monolith.

- PostgreSQL: authoritative application state.
- Redis: queues/cache/locks; never domain truth.
- Object storage: large artifacts/documents.
- Asynchronous workers: long-running cognition/investigation/action.
- Every execution is traceable by correlation/execution identity.

## 33. Event Architecture

Domain events are typed and versioned.

Minimum envelope:

- event_id
- event_type
- event_version
- tenant_id
- occurred_at
- recorded_at
- correlation_id
- causation_id
- actor
- source
- payload

Events are immutable.

## 34. Security

Foundational requirements:

- tenant isolation;
- source-level authorization;
- least privilege;
- credential isolation;
- encryption;
- auditability;
- action authorization;
- provenance;
- retention/deletion policies;
- model-provider data boundaries.

## 35. Architecture Invariants

A1. Events and observations are immutable.
A2. Beliefs are versioned.
A3. Inferences cannot be represented as observations.
A4. LLM output cannot directly become authoritative fact.
A5. Consequential beliefs have provenance.
A6. Unknown is first-class.
A7. Contradictory evidence is retained.
A8. Confidence does not replace provenance.
A9. Historical beliefs are not silently rewritten.
A10. Goals are distinct from beliefs and attention policy.
A11. Policy engine owns authorization.
A12. LLMs cannot bypass action policy.
A13. Agents cannot directly mutate authoritative workflow state.
A14. Modules communicate through public contracts.
A15. Cross-module internal imports are forbidden.
A16. Provider implementations stay behind gateways.
A17. No business/domain state may require a specific AI/LLM provider or model.
A18. AI/LLM providers and models are hot-swappable without domain migration.
A19. Provider/model metadata for completed executions is retained for audit only.
A20. Long-running work is asynchronous.
A21. Every execution is traceable.
A22. Actions are idempotent where applicable.
A23. Learned preferences cannot silently override explicit policy.
A24. Learned models are versioned/auditable.
A25. Employment-impacting recommendations are recommendations, not autonomous employment decisions.
A26. Material conclusions expose evidence and uncertainty.
A27. Connector implementations cannot leak provider-specific state into domain modules.
A28. Extension runtime capabilities are general-purpose within sandbox/policy boundaries.
A29. Notification delivery cannot become authoritative domain state.
A30. Audit records are append-only from the domain perspective.

## 36. Non-Frozen Implementation Choices

The following remain implementation choices:

- LLM/AI provider;
- model family and model version;
- embedding model/provider;
- vector store;
- graph database;
- WhatsApp provider;
- telephony provider;
- web search provider;
- external data providers;
- frontend framework/components;
- queue implementation;
- deployment vendor.

Architecture freezes capabilities and boundaries, not vendors.
""