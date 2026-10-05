# Architecture Writing / Engineering Skill v1.7

v1.7 is an Architecture Reasoning Engine layered on top of Architecture Intelligence and Architecture Governance, with a separate Writing Style presentation layer.

## Capability model

```text
Repository
  ↓
Observations
  ↓
Architecture Intelligence
  ↓
Problem Classification
  ↓
Reasoning Method Selection
  ↓
Structured Analysis
  ↓
Decision Model
  ↓
Governance
  ↓
Artifacts / CI
```

## What changed in v1.7

- Added a decoupled Writing Style integration layer.
- Added artifact-specific writing profiles.
- Added style-boundary and traceability checks.
- Added Anti-AI as a presentation quality gate rather than a reasoning method.
- Preserved the v1.6 decision model as the single source of truth.

## What changed in v1.6

- Added reasoning method catalog.
- Added method selection and composition.
- Added `reasoning-plan.json` style intermediate model.
- Added evidence/assumption/unknown discipline for reasoning.
- Added reusable method contracts.
- Connected reasoning to Architecture Intelligence, Decision Model, and Governance.
- Added reasoning quality gates and examples.

## Design principle

The skill does not ask an agent to "use SCQA" everywhere. It asks the agent to select the smallest useful method chain for the problem.

## Dependency

The preferred renderer is the standalone `writing-style` Skill. Architecture Writing provides a safe local fallback when it is unavailable.
