# Architecture Writing / Engineering Skill

## What this is

`architecture-writing` is an Architecture Engineering Agent Skill. It is designed to take an architecture problem from **intent and evidence** through **analysis, modeling, reasoning, design, documentation, review, migration, and governance**.

This package is the **v1.7 complete capability reconstruction**. It does not introduce a new version number. The purpose is to restore capabilities that were accumulated from v1.0 through v1.7 but became too compressed or disconnected during later iterations.

The central design decision is:

> **Architecture Writing is the complete engineering system; Reasoning Runtime is an execution layer inside it.**

The agent fills `recommended_option`. `human_decision` stays `pending` until a person confirms, rejects, or modifies it.

## Capability architecture

```text
                         Architecture Knowledge Model
                                      │
          ┌───────────────┬───────────┼───────────┬───────────────┐
          ↓               ↓           ↓           ↓               ↓
      Discovery        Modeling    Drivers   Intelligence     Tooling
          │               │           │           │               │
          └───────────────┴───────────┴───────────┴───────────────┘
                                      ↓
                             Architecture Reasoning
                                      │
                         ┌────────────┴────────────┐
                         ↓                         ↓
                     Planner                    Runtime
                         │                         │
                         └────────────┬────────────┘
                                      ↓
                              Evidence / Analysis
                                      ↓
                              Options / Trade-offs
                                      ↓
                               Recommendation
                                      ↓
                               Human Decision
                                      ↓
                                  Design
                           ┌──────────┼──────────┐
                           ↓          ↓          ↓
                       Writing    Diagrams      ADR
                           └──────────┼──────────┘
                                      ↓
                                Review / QA
                                      ↓
                              Migration / Evolution
                                      ↓
                                  Governance
```

## Capability layers

| Layer | Responsibility |
|---|---|
| `core/` | Canonical architecture knowledge, decision, evidence, workflow, lifecycle models |
| `discovery/` | Requirements, repository, system, and architecture assessment |
| `modeling/` | Architecture entities, boundaries, dependencies, flows, ownership, graph |
| `drivers/` | Business drivers, quality attributes, constraints, assumptions, architecture drivers |
| `intelligence/` | Diff, smells, boundary candidates, driver inference, change impact, confidence |
| `reasoning/` | Reasoning methods, selection, composition, DSL, planner, runtime, evidence, synthesis |
| `design/` | Option generation, trade-offs, decision analysis, tactics, consequences |
| `diagrams/` | Mermaid-first architecture visualization |
| `writing/` | Architecture storytelling, document structure, technical writing, audience adaptation |
| `review/` | Architecture, consistency, quality, and risk review |
| `migration/` | Migration strategy, transition planning, data migration, rollback, validation |
| `governance/` | Principles, rules, fitness functions, compliance, exceptions, policy |
| `tooling/` | Repository scanning, dependency analysis, graphing, agent orchestration, artifact generation, ADR synchronization |
| `templates/` | Reusable architecture document contracts |
| `checklists/` | Quality and execution gates |
| `workflows/` | End-to-end task recipes |
| `examples/` | Concrete examples of decisions and runtime execution |

## Canonical workflow

For substantial architecture work:

```text
1. Discover
2. Model
3. Identify drivers
4. Assess intelligence signals
5. Frame the problem
6. Select reasoning methods
7. Execute reasoning
8. Generate and compare options
9. Decide
10. Design
11. Project the model into documents/diagrams/ADR
12. Validate and review
13. Plan migration/evolution
14. Apply governance
```

The smallest valid workflow may skip stages that are irrelevant to the task, but must not skip evidence or decision-critical validation merely for convenience.

## Canonical architecture story

Every major document should be traceable through:

`Context → Problem → Requirements → Constraints → Drivers → Current State → Gap → Options → Trade-offs → Decision → Consequences → Risks → Validation → Migration → Evolution`

## Evidence model

The skill deliberately distinguishes:

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

Evidence sources include repository/code, runtime metrics, tests, configuration, explicit requirements, documentation, external references, and expert judgment. Unknown remains explicit.

## Reasoning Runtime

The Runtime executes a machine-readable reasoning plan. It supports:

- method selection;
- method composition;
- evidence registration;
- intermediate results;
- contradiction detection;
- sensitivity analysis;
- confidence propagation;
- synthesis;
- reproducible execution.

The Runtime does **not** replace architecture analysis, design, writing, review, or migration.

## Reasoning methods

The package retains the method families developed during v1.6:

- problem structuring: SCQA, MECE, 5W1H, Logic Tree;
- root cause: 5 Whys, Causal Chain, Fishbone;
- comparison/decision: 2D Matrix, Decision Matrix, Cost-Benefit, Risk Matrix, Reversibility;
- prioritization: Impact-Effort, Pareto;
- uncertainty: Scenario Analysis, Sensitivity Analysis.

Use methods selectively. A method must support a concrete reasoning objective and must not manufacture evidence.

## Mermaid-first diagrams

The diagram layer intentionally remains Mermaid-first and covers:

- context;
- container;
- component;
- sequence;
- deployment;
- data flow;
- integration;
- migration.

Diagrams are projections of the architecture model. They are not independent sources of truth.

## Typical outputs

The skill can produce:

- architecture overview;
- system design;
- service design;
- integration design;
- data architecture;
- deployment architecture;
- security architecture;
- reliability design;
- performance design;
- technical proposal;
- ADR;
- architecture review;
- migration plan;
- governance report;
- architecture diagrams.

## Existing-system workflow

For repository-based work, prefer:

```text
Repository
 → Build / Module Detection
 → Dependency Extraction
 → Framework / API / Persistence / Messaging Detection
 → Architecture Graph
 → Evidence Ledger
 → Intelligence
 → Assessment
 → Reasoning
 → Decision
```

Do not infer unseen behavior simply because a framework or dependency is present.

## Greenfield workflow

For new systems:

```text
Business Intent
 → Requirements
 → Constraints
 → Architecture Drivers
 → Quality Scenarios
 → Options
 → Trade-offs
 → Decision
 → Design
 → Validation
 → Delivery / Migration
```

## Change / migration workflow

```text
Current State
 → Architecture Diff
 → Impact
 → Options
 → Decision
 → Transition States
 → Compatibility
 → Migration Units
 → Validation
 → Cutover
 → Rollback
 → Decommission
```

## Governance workflow

```text
Principle
 → Rule
 → Fitness Function / Policy
 → Check
 → Violation
 → Exception / Remediation
 → Governance Report
```

`UNKNOWN` is not automatically `FAIL`.

## File selection guidance

Start from `SKILL.md`, then load only the domain needed:

- architecture semantics → `core/`, `modeling/`;
- repository/system analysis → `discovery/`, `tooling/`;
- decision reasoning → `drivers/`, `intelligence/`, `reasoning/`, `design/`;
- architecture documentation → `writing/`, `templates/`;
- diagrams → `diagrams/`;
- review → `review/`, `checklists/`;
- migration → `migration/`, `templates/migration-plan.md`;
- governance → `governance/`, `workflows/architecture-governance.md`.

## Package completeness

This reconstruction deliberately preserves the v1.6 reasoning/governance assets alongside the broader architecture-writing base. In particular, it retains:

- reasoning method-specific files;
- reasoning selection/composition contracts;
- governance schemas;
- architecture-diff schema;
- runtime schemas;
- reasoning workflows;
- PR/governance workflows;
- examples and execution plans.

No capability should be removed simply because a later layer was introduced.

## Quality standard

A high-quality output is not the longest document. It is an artifact set in which:

1. the problem is explicit;
2. requirements and constraints are separated;
3. drivers explain why architecture properties matter;
4. evidence supports consequential claims;
5. alternatives and trade-offs are visible;
6. decisions have consequences and risks;
7. diagrams agree with prose and model;
8. validation is concrete;
9. migration is safe enough to execute;
10. governance status is explicit;
11. uncertainty is not hidden.

## Evolution history

See [`CHANGELOG.md`](CHANGELOG.md) for the complete v1.0–v1.7 evolution and the capability inheritance restored by this reconstruction.
