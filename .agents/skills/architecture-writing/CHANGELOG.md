# Changelog — Architecture Writing / Engineering Skill

This changelog records the evolution from **v1.0 through v1.7**. The current package is a **v1.7 complete capability reconstruction** and does not introduce a new version number.

The purpose of this file is to make capability inheritance explicit: later layers extend earlier capabilities; they do not replace them.

The agent may fill `recommended_option`. `human_decision` stays `pending` until a person confirms, rejects, or modifies it.

---

## v1.0 — Architecture Writing Skill

### Goal

Establish a reusable architecture-document writing methodology rather than generic technical prose generation.

### Core workflow

```text
Business / Product Drivers
 → Problem
 → Requirements
 → Constraints
 → Architecture Drivers
 → Options
 → Trade-offs
 → Decision
 → Consequences
 → Validation
 → Evolution
```

### Capabilities introduced

- architecture reasoning fundamentals;
- architecture storytelling;
- trade-off analysis;
- quality-attribute thinking;
- architecture diagrams;
- architecture review;
- technical writing;
- architecture anti-patterns;
- reusable architecture-design, proposal, overview, ADR, review, and migration templates;
- architecture, writing, and review checklists;
- examples of good/bad architecture writing and trade-off reasoning.

### Architectural principle

Architecture documents should explain **why the architecture exists**, not merely describe components.

---

## v1.1 — Architecture Work Workflow

### Goal

Expand the skill from document writing into a repeatable architecture-engineering workflow.

### Capabilities added

- repository architecture analysis;
- architecture boundary analysis;
- architecture option generation;
- decision matrices;
- multi-audience architecture output;
- architecture evolution;
- repository assessment template;
- decision-matrix template;
- repository and decision-quality checklists.

### Key shift

```text
Write Architecture Document
        ↓
Perform Architecture Work
        ↓
Generate Document From Work
```

The repository became an important evidence source for existing-system architecture work.

---

## v1.2 — Architecture Agent Execution Contract

### Goal

Make architecture work executable as an Agent workflow with a shared internal decision model.

### Canonical execution pipeline

```text
DISCOVER
   ↓
ANALYZE
   ↓
DESIGN
   ↓
GENERATE
   ↓
VALIDATE
```

### Structured internal model introduced

The model established fields for:

- context;
- problem;
- goals / non-goals;
- constraints;
- architecture drivers;
- current state;
- boundaries;
- critical flows;
- options;
- trade-offs;
- decision;
- consequences;
- risks;
- assumptions;
- evidence;
- validation;
- migration;
- open questions.

### Capabilities added

- agent workflow contract;
- architecture smell detection;
- Mermaid generation guidance;
- ADR linkage;
- validation strategy;
- architecture assessment template;
- ADR-linked design template;
- agent-output template;
- agent-run example and checklist.

### Key principle

All major artifacts should derive from the same decision model so that diagrams, ADRs, architecture documents, and migration plans do not drift apart.

---

## v1.3 — Architecture Tooling Layer

### Goal

Move from a purely descriptive Agent skill toward an evidence-producing and artifact-synchronizing tool layer.

### Tooling architecture

```text
Repository
 → Scanner
 → Observations
 → Dependency Analyzer
 → Architecture Graph
 → Reasoning
 → Decision Model
 → Artifact Generator
 → ADR Sync
```

### Capabilities added

- repository scanner;
- dependency analyzer;
- architecture graph;
- architecture agent orchestration;
- ADR synchronization;
- artifact generation;
- machine-readable observations;
- architecture graph schema;
- decision model schema;
- full architecture review workflow;
- greenfield design workflow;
- existing-system improvement workflow;
- tooling-quality checklist.

### Key principle

Tools acquire and transform evidence; they must not silently invent architecture decisions.

---

## v1.4 — Architecture Intelligence Layer

### Goal

Add architectural inference and change intelligence on top of repository observations and architecture graphs.

### Capabilities added

- Architecture Diff;
- Boundary Candidate Detection;
- Architecture Smell Inference;
- Architecture Driver Inference;
- Change Impact Analysis;
- evidence confidence model.

### Architecture Diff categories

- added/removed components;
- added/removed dependencies;
- boundary crossings;
- data ownership changes;
- synchronous/asynchronous edge changes;
- external dependency changes;
- deployment coupling changes;
- trust-boundary changes.

### Severity model

- BLOCKER;
- MAJOR;
- MINOR;
- INFO.

### Evidence confidence

- direct evidence → HIGH;
- strong inference → HIGH/MEDIUM;
- weak inference → LOW;
- insufficient evidence → UNKNOWN.

### Change-impact model

```text
Change
 → Mechanism
 → Architecture Property
 → Potential Consequence
```

### Key safety constraints

- smell ≠ decision;
- boundary candidate ≠ service extraction;
- inferred driver ≠ requirement;
- dependency ≠ failure;
- code diff ≠ architecture change without interpretation.

---

## v1.5 — Architecture Governance

### Goal

Turn architecture principles into enforceable, inspectable governance without allowing governance to become an architecture decision engine.

### Governance chain

```text
Architecture Principle
 → Architecture Rule
 → Fitness Function / Policy
 → Compliance Check
 → Violation
 → Exception / Remediation
 → Governance Report
```

### Capabilities added

- architecture principles;
- architecture rules;
- fitness functions;
- compliance engine;
- policy-as-data;
- PR/CI/release architecture checks;
- governance reports;
- exception management;
- governance schemas.

### Exception model

Exceptions should record:

- reason;
- scope;
- owner;
- expiry;
- compensating control;
- approval.

### Key principle

Governance checks whether an architecture conforms to established rules. It does not invent a new architecture decision.

---

## v1.6 — Architecture Reasoning Engine

### Goal

Turn architecture reasoning methods into a composable reasoning system instead of a list of writing techniques.

### Reasoning architecture

```text
Architecture Intelligence
        ↓
Problem Classification
        ↓
Reasoning Method Selection
        ↓
Method Composition
        ↓
Evidence-driven Analysis
        ↓
Synthesis
        ↓
Decision Model
        ↓
Governance
        ↓
Artifacts
```

### Reasoning methods introduced/standardized

#### Problem structuring

- SCQA;
- MECE;
- 5W1H;
- Logic Tree.

#### Root cause / causal reasoning

- 5 Whys;
- Causal Chain;
- Fishbone.

#### Comparison / decision

- 2D Matrix;
- Decision Matrix;
- Cost-Benefit;
- Risk Matrix;
- Reversibility Analysis.

#### Prioritization

- Impact-Effort;
- Pareto.

#### Uncertainty

- Scenario Analysis;
- Sensitivity Analysis.

### Method-selection principles

- select methods based on the problem and objective;
- do not mechanically apply all methods;
- methods cannot create facts;
- unknown remains unknown;
- matrix scores require criteria and evidence or explicit expert judgment;
- SCQA is synthesis/communication, not decision evidence;
- contradictions must remain visible;
- consequential conclusions must trace to evidence, assumptions, or explicit decision rules.

### Governance integration

Reasoning was explicitly connected to governance without making governance responsible for architecture decisions.

---

## v1.7 — Architecture Reasoning Runtime

### Goal

Turn the v1.6 reasoning plan into an executable runtime while preserving the complete architecture-engineering system around it.

### Runtime architecture

```text
Architecture Intelligence
        ↓
Problem Classification
        ↓
Reasoning Planner
        ↓
Reasoning Plan
        ↓
Plan Validation
        ↓
Reasoning Executor
        ↓
Evidence Ledger
        ↓
Intermediate Results
        ↓
Contradiction Check
        ↓
Sensitivity Analysis
        ↓
Synthesis
        ↓
Decision Candidate
        ↓
Confidence
        ↓
Governance
        ↓
Artifacts
```

### Runtime states

- DRAFT;
- READY;
- RUNNING;
- BLOCKED;
- COMPLETED;
- COMPLETED_WITH_UNKNOWN;
- FAILED.

### Runtime invariants

1. A step cannot consume unregistered evidence.
2. A reasoning method cannot create factual evidence.
3. Derived claims reference source evidence or previous derived results.
4. UNKNOWN remains explicit.
5. Low-confidence intermediate results cannot silently become high-confidence decisions.
6. Governance evaluates established rules rather than inventing decisions.
7. Equivalent inputs, plans, method versions, and configuration should be reproducible.

### Runtime contracts added

- reasoning plan schema;
- runtime result schema;
- method contracts;
- planner;
- executor;
- evidence ledger;
- contradiction analysis;
- sensitivity analysis;
- synthesis.

---

# v1.7 Complete Capability Reconstruction

This is the current package state.

It does **not** introduce a v1.8 or any other new version. It repairs the inheritance chain that became too thin in the earlier v1.7 Runtime-focused implementation.

## Capabilities restored

### Architecture Writing

Restored complete architecture-story structure, technical writing guidance, audience adaptation, document structures, and architecture-document templates.

### Architecture Analysis

Restored requirement analysis, repository analysis, system analysis, architecture assessment, and evidence-grounded existing-system workflows.

### Architecture Modeling

Restored architecture entities, boundaries, dependencies, flows, ownership, and architecture graph concepts.

### Architecture Drivers

Restored business drivers, quality attributes, constraints, assumptions, and architecture-driver engineering.

### Architecture Intelligence

Restored architecture diff, smells, boundary candidates, driver inference, change impact, and confidence.

### Architecture Reasoning

Restored method-specific reasoning assets from v1.6 instead of collapsing them into one generic method catalog.

### Reasoning Runtime

Embedded the v1.7 runtime as an execution layer over the restored knowledge/model/evidence system.

### Architecture Design

Restored option generation, trade-offs, decision analysis, tactics, and consequence analysis.

### Architecture Diagrams

Restored Mermaid-first context, container, component, sequence, deployment, data-flow, integration, and migration diagrams.

### Architecture Review

Restored architecture, consistency, quality, and risk review capabilities plus quality checklists.

### Migration

Restored migration strategy, planning, data migration, rollback, and validation.

### Governance

Preserved principles, rules, fitness functions, compliance, policy, and exception handling from the governance line.

### Tooling

Restored repository scanner, dependency analyzer, architecture graph, architecture agent, ADR sync, and artifact generator.

### Artifact ecosystem

Restored reusable templates, checklists, workflows, examples, schemas, and manifests.

## Reconstruction principles

1. **No capability loss through layering.** Runtime extends the skill; it does not replace prior capabilities.
2. **One model, many projections.** Documents, diagrams, ADRs, migration plans, and governance reports should derive from the same architecture/decision model.
3. **Evidence before inference.** Architecture intelligence and reasoning must expose evidence lineage.
4. **Unknown is first-class.** Missing evidence is not permission to invent certainty.
5. **Methods are subordinate to objectives.** SCQA, MECE, matrices, causal methods, and scenario methods are tools, not rituals.
6. **Governance is a constraint layer.** It does not become the architecture decision maker.
7. **Migration is architecture.** A target architecture without a credible transition path is incomplete for change-heavy work.
8. **Diagrams are model projections.** A beautiful diagram that contradicts the architecture model is a defect.
9. **Tooling acquires and synchronizes evidence.** It does not bypass reasoning or decision traceability.
10. **Do not add concepts merely for version growth.** Future changes should first prove that the current capability model is insufficient.

## File inheritance policy

The reconstruction deliberately preserves the useful v1.6 files even where the new structure provides a more consolidated home. This is intentional: method-specific reasoning files, governance schemas, workflow assets, and examples remain available so that no prior capability is silently lost.

When a capability exists in both a consolidated file and a historical specialized file, prefer the consolidated contract for orchestration and retain the specialized file for method/domain detail and backward compatibility.
