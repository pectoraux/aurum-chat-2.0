# Aurum 2.0 — Frozen Architecture Specification

**Status:** Proposed for Freeze  
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

## 8. Learned Company Model

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

## 9. Environmental Intelligence

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

## 10. Presence and Activity Intelligence

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

## 11. Process Intelligence

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

## 12. Capability Graph

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

## 13. Workforce Intelligence

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

## 14. Supplier and External Workforce Intelligence

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

## 15. Investigation Engine

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

## 16. Transactive Organizational Memory

Aurum maintains knowledge of who:

- knows;
- owns;
- has experience with;
- possesses a capability;
- works on;
- decides;
- influences.

This lets Aurum investigate through the right people.

## 17. Agent Workforce

Agents are organizational actors, not merely LLM calls.

Lifecycle:

PROPOSED → MD APPROVAL → RECRUITED → ACTIVE → EVALUATED → RETAIN / MODIFY / TERMINATE.

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

## 18. Agent Termination

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

## 19. Extension / Software Builder

Aurum can identify opportunities for arbitrary software capabilities.

Lifecycle:

observed problem → process model → opportunity → software feasibility → design → approval → builder → verification → deployment → outcome observation.

The extension system must not be artificially constrained to a predefined list of feature types.

## 20. Action Authority

Aurum distinguishes:

- OBSERVE
- ANALYZE
- RECOMMEND
- ASK
- PROPOSE
- EXECUTE

Company policy determines which require approval.

LLMs and agents cannot bypass action policy.

## 21. Learning

Learning incorporates:

- explicit feedback;
- behavioral feedback;
- outcome feedback;
- prediction feedback;
- source feedback;
- agent performance;
- investigation efficiency.

Learned models are versioned and auditable.

## 22. Cognitive Loop

REALITY
→ PERCEIVE
→ MEMORY
→ WORLD MODEL
→ EPISTEMICS
→ INVESTIGATE when necessary
→ ATTENTION + LEARN
→ INFORM / RECOMMEND / ACT
→ HUMAN / AGENT / SOFTWARE
→ OUTCOME
→ LEARN
→ WORLD MODEL

## 23. Module Boundaries

Initial ownership modules:

- auth
- organizations
- people
- world
- events
- observations
- memory
- epistemics
- attention
- investigation
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

## 24. Infrastructure

Initial deployment is a modular monolith.

- PostgreSQL: authoritative application state.
- Redis: queues/cache/locks; never domain truth.
- Object storage: large artifacts/documents.
- Asynchronous workers: long-running cognition/investigation/action.
- Every execution is traceable by correlation/execution identity.

## 25. Event Architecture

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

## 26. LLM Architecture

LLMs are replaceable cognitive providers.

Domain modules must not directly depend on a provider.

Cognitive Service → LLM Gateway → provider adapters.

LLM output is never authoritative merely because it came from an LLM.

## 27. Agents vs LLMs

LLM = reasoning capability.

Agent = actor capable of performing actions.

Agents may use one or more LLMs.

## 28. Security

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

## 29. Auditability

Every consequential action should answer:

- What did Aurum know?
- What did it believe?
- What evidence supported it?
- What did it not know?
- What policy applied?
- What threshold was crossed?
- What was recommended?
- Who approved it?
- What executed?
- What happened afterward?

## 30. Architecture Invariants

A1. Events and observations are immutable.
A2. Beliefs are versioned.
A3. Inferences cannot be represented as observations.
A4. LLM output cannot directly become authoritative fact.
A5. Consequential beliefs have provenance.
A6. Unknown is first-class.
A7. Contradictory evidence is retained.
A8. Confidence does not replace provenance.
A9. Historical beliefs are not silently rewritten.
A10. Policy engine owns authorization.
A11. LLMs cannot bypass action policy.
A12. Agents cannot directly mutate authoritative workflow state.
A13. Modules communicate through public contracts.
A14. Cross-module internal imports are forbidden.
A15. Provider implementations stay behind gateways.
A16. Long-running work is asynchronous.
A17. Every execution is traceable.
A18. Actions are idempotent where applicable.
A19. Learned preferences cannot silently override explicit policy.
A20. Learned models are versioned/auditable.
A21. Employment-impacting recommendations are recommendations, not autonomous employment decisions.
A22. Material conclusions expose evidence and uncertainty.

## 31. Non-Frozen Implementation Choices

The following remain implementation choices:

- LLM provider;
- embedding model;
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
