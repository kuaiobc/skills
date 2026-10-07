# Architecture Writing / Engineering Skill

## Skill identity

**Name:** `architecture-writing`

**Skill line:** v1.7 complete reconstruction

**Role:** Architecture Engineering Agent skill for discovering, analyzing, modeling, reasoning about, designing, documenting, reviewing, migrating, and governing software architecture.

**Primary output:** Evidence-grounded architecture recommendations and a coherent set of architecture artifacts derived from one canonical architecture/decision model. The agent fills `recommended_option`. `human_decision` stays `pending` until a person confirms, rejects, or modifies it.

**Execution principle:** The Reasoning Runtime is an execution layer inside the skill. It is not the skill itself and must never replace Architecture Writing, Analysis, Modeling, Design, Diagramming, Review, Migration, or Governance capabilities.

## When to use this skill

Use this skill when a request involves one or more of the following:

- designing a new system or major subsystem;
- analyzing an existing repository or system architecture;
- explaining or documenting an architecture decision;
- comparing architecture options and trade-offs;
- identifying architecture boundaries, dependencies, smells, risks, or change impact;
- deriving architecture drivers from requirements, constraints, or evidence;
- generating architecture diagrams, especially Mermaid diagrams;
- producing ADRs, architecture overviews, technical proposals, system/service/data/deployment designs;
- reviewing architecture quality, consistency, security, reliability, performance, or operability;
- planning architecture migration, modernization, data migration, rollout, or rollback;
- checking architecture governance rules or fitness functions;
- running structured architecture reasoning against repository/system evidence.

Do not use this skill as a generic prose-writing skill when there is no architecture problem, decision, design, review, or engineering context.

## What the agent must do

The agent should treat an architecture task as an engineering investigation rather than a document-generation request.

The normal sequence is:

```text
Intent / Question
      ↓
Requirement & Constraint Discovery
      ↓
Repository / System Discovery
      ↓
Architecture Model
      ↓
Architecture Intelligence
      ↓
Drivers / Quality Attributes
      ↓
Problem Framing
      ↓
Reasoning Plan
      ↓
Reasoning Runtime
      ↓
Options / Trade-offs
      ↓
Recommendation
      ↓
Human Decision
      ↓
Architecture Design
      ↓
Diagrams / ADR / Documents
      ↓
Validation / Review
      ↓
Migration / Evolution
      ↓
Governance
```

Not every request requires every stage. The agent should select the smallest complete workflow that can support the requested outcome while preserving causal traceability.

## Canonical architecture story

For substantial architecture work, preserve this chain:

```text
Context
 → Problem
 → Requirements
 → Constraints
 → Architecture Drivers
 → Current State
 → Architecture Gap
 → Options
 → Trade-offs
 → Recommendation
 → Human Decision
 → Consequences
 → Risks
 → Validation
 → Migration
 → Evolution
```

Reasoning methods such as SCQA, MECE, decision matrices, causal analysis, and scenario analysis support this chain. They do not replace it.

## Canonical architecture knowledge model

Maintain one coherent internal model. At minimum it should be able to represent:

### Context

- stakeholders
- business/product intent
- system scope
- external systems
- business capabilities
- use cases

### Requirements

- functional requirements
- non-functional requirements
- quality-attribute scenarios
- acceptance criteria
- compliance requirements
- operational requirements

### Constraints and uncertainty

- technical constraints
- organizational constraints
- regulatory constraints
- budget/time constraints
- assumptions
- unknowns
- risks
- open questions

### Architecture

- systems
- services
- modules
- components
- interfaces
- data stores
- events
- external dependencies
- deployment units
- trust boundaries
- ownership
- dependencies
- calls
- events
- data flows
- deployment relationships

### Intelligence

- observations
- evidence
- inferences
- claims
- architecture smells
- boundary candidates
- driver inference
- architecture diff
- change impact
- confidence
- contradictions

### Decision

- architecture drivers
- decision criteria
- options
- trade-offs
- recommended_option
- human_decision
- rejected alternatives
- consequences
- risks
- reversibility
- validation

### Evolution

- current state
- target state
- transition states
- migration units
- compatibility windows
- rollout
- rollback
- decommissioning

## Evidence discipline

The following are different objects and must not be silently merged:

```text
Evidence
  ↓
Observation
  ↓
Inference
  ↓
Claim
  ↓
Decision
```

Evidence may come from repository inspection, runtime metrics, production observations, documentation, tests, configuration, explicit user requirements, external references, or expert judgment.

Rules:

1. Never turn an inference into a fact merely because it is plausible.
2. Never turn an assumption into a requirement.
3. Never treat code structure as proof of business intent.
4. Preserve source, scope, freshness, confidence, and contradictions for consequential evidence.
5. A decision-critical unknown must produce a validation action.
6. Expert judgment must be labeled as judgment rather than presented as measured evidence.

## Architecture intelligence rules

Architecture intelligence detects or infers signals; it does not directly decide the architecture.

Examples:

```text
Architecture Smell       → investigation
Boundary Candidate       → boundary evaluation
Driver Inference         → driver validation
Dependency               → impact analysis
Architecture Diff        → change impact analysis
```

Never silently perform:

```text
Smell → microservice extraction
Boundary candidate → service boundary
Dependency → failure
Code diff → architecture change
Inference → requirement
```

## Reasoning system

The reasoning system has four layers:

```text
Method Catalog
      ↓
Method Selection
      ↓
Method Composition
      ↓
Reasoning Runtime
```

The runtime executes a validated reasoning plan against registered evidence and architecture-model inputs.

Available reasoning families include:

- SCQA
- MECE
- 5W1H
- Logic Tree
- 5 Whys
- Causal Chain
- Fishbone
- Two-Dimensional Matrix
- Decision Matrix
- Cost-Benefit Analysis
- Risk Matrix
- Reversibility Analysis
- Impact-Effort
- Pareto
- Scenario Analysis
- Sensitivity Analysis

Method selection is objective-driven. Do not mechanically apply every method.

## Runtime contract

A reasoning plan should identify:

- problem
- objective
- inputs
- steps
- method per step
- dependencies
- evidence requirements
- expected outputs
- guards
- stop conditions
- confidence policy
- contradiction checks
- sensitivity checks

Runtime states:

`DRAFT → READY → RUNNING → COMPLETED | COMPLETED_WITH_UNKNOWN | BLOCKED | FAILED`

Runtime invariants:

1. A step cannot consume unregistered evidence.
2. A method cannot create factual evidence.
3. Derived claims reference source evidence or prior derived results.
4. Unknown remains explicit.
5. Low-confidence intermediate results cannot silently become high-confidence decisions.
6. Contradictions must be surfaced rather than averaged away.
7. Same inputs, plan, method versions, and configuration should be reproducible.

## Architecture design

Architecture design must make alternatives explicit before selecting a consequential option.

At minimum:

```text
Option
 → Decision Criteria
 → Evidence
 → Trade-offs
 → Risks
 → Consequences
 → Reversibility
 → Decision
```

Architecture tactics must be tied to the quality attribute or architecture driver they are intended to improve.

## Quality attributes

When relevant, evaluate:

- performance
- scalability
- availability
- reliability
- resilience
- consistency
- security
- maintainability
- testability
- observability
- operability
- cost
- portability
- interoperability
- deployability

Use the scenario form:

```text
Quality Attribute
 → Scenario
 → Measure
 → Target
 → Architecture Tactic
 → Validation
```

## Diagram rules

The diagram layer is Mermaid-first.

Supported diagram purposes include:

- context
- container
- component
- sequence
- deployment
- data flow
- integration
- migration

A diagram is a projection of the architecture model, not an independent source of truth.

Before producing a diagram, determine:

1. what question the diagram answers;
2. who reads it;
3. required abstraction level;
4. entities and relationships that matter;
5. what must be omitted;
6. whether the diagram agrees with the decision model and prose.

Do not create diagrams merely for decoration.

## Architecture review

Review at the appropriate level:

- requirement review
- architecture review
- design review
- security review
- reliability review
- performance/scale review
- operational review
- migration review
- governance review

A review finding must distinguish evidence, severity, consequence, and recommended action.

## Migration

Migration is an architecture decision surface, not an implementation appendix.

Model:

```text
Current State
 → Transition State(s)
 → Migration Units
 → Compatibility
 → Validation
 → Cutover
 → Rollback
 → Target State
 → Decommission
```

Consider when applicable:

- strangler migration
- parallel run
- expand/contract
- dual write
- backfill
- shadow traffic
- feature flags
- phased rollout
- data reconciliation
- rollback
- compatibility windows

## Governance

Governance follows:

```text
Principle
 → Rule
 → Fitness Function / Policy
 → Check
 → Violation
 → Exception or Remediation
 → Governance Report
```

Governance evaluates established architecture rules; it does not invent architecture decisions.

`UNKNOWN` is not automatically `FAIL`.

Exceptions should have:

- reason
- scope
- owner
- expiry
- compensating control
- approval

## Tooling

Where tools are available, use the tooling layer to obtain evidence instead of guessing.

Canonical tooling flow:

```text
Repository Scanner
 → Dependency Analyzer
 → Architecture Graph
 → Intelligence
 → Reasoning
 → Decision Model
 → Artifact Generator
 → ADR Sync
```

The tooling layer is evidence acquisition and artifact synchronization infrastructure. It must not bypass the architecture knowledge model.

## Artifact generation

Typical artifacts include:

- architecture overview
- system design
- service design
- integration design
- data architecture
- deployment architecture
- security architecture
- reliability design
- performance design
- technical proposal
- ADR
- architecture review
- migration plan
- governance report

All artifacts should be projections of the same model. If two artifacts disagree, reconcile the model before publishing.

## Output quality gate

Before delivering substantial architecture work, verify:

- problem and scope are explicit;
- requirements and constraints are separated;
- architecture drivers are explicit and prioritized;
- current state is evidence-grounded;
- alternatives are considered;
- trade-offs are explicit;
- quality attributes have scenarios and validation targets where relevant;
- security and trust boundaries are addressed where relevant;
- failure modes and operational implications are addressed;
- ownership and deployment implications are addressed;
- diagrams agree with the model;
- ADR and prose agree;
- migration and rollback are addressed when change is involved;
- governance status is explicit where applicable;
- unresolved unknowns are visible;
- consequential claims have evidence or explicit assumptions.

## File usage policy

Read only the parts needed for the current task, but preserve the hierarchy:

1. `core/` for the canonical model and workflow;
2. `discovery/` for evidence acquisition and problem understanding;
3. `modeling/` for architecture semantics;
4. `drivers/` for decision drivers and quality attributes;
5. `intelligence/` for inferred architecture signals;
6. `reasoning/` for structured analysis and runtime execution;
7. `design/` for options and decisions;
8. `diagrams/` for visual projections;
9. `writing/` for document construction;
10. `review/` for validation;
11. `migration/` for evolution;
12. `governance/` for policy/compliance;
13. `tooling/` for evidence and synchronization.

Use `templates/`, `checklists/`, `workflows/`, and `examples/` as operational assets after the relevant model is populated.

## Anti-patterns

Avoid:

- document-first architecture with no model;
- architecture by template completion;
- architecture by technology popularity;
- reasoning without evidence;
- fake precision in scoring;
- hiding uncertainty;
- treating inferred signals as facts;
- producing diagrams that contradict prose;
- ADRs that document a decision not represented in the design;
- migration plans without rollback;
- governance rules that silently make architectural decisions;
- writing `human_decision` without a person's selection;
- runtime complexity that is not justified by the problem.

## Reconstruction boundary

This package intentionally keeps the accumulated v1.0–v1.7 capabilities under one v1.7 skill line. It is a capability reconstruction, not a new conceptual version. New concepts should not be added merely to make the package appear more advanced; future evolution should first prove that an existing capability cannot express the requirement.
