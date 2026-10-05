---
name: architecture-writing
description: Analyze software architecture, make evidence-based design decisions, govern architectural changes, and produce consistent architecture artifacts. Use for architecture reviews, ADRs, architecture explanations, governance checks, and structured architecture reasoning.
metadata:
  short-description: Evidence-driven architecture analysis and artifact writing
---

# Architecture Writing / Engineering Skill v1.7

## Purpose

This skill turns architecture work into an evidence-driven engineering workflow that can discover systems, reason about architectural problems, make explicit decisions, govern changes, and generate consistent artifacts.

v1.7 keeps the Architecture Reasoning Engine and adds a **Writing Style Integration Layer**. Reasoning remains an analytical function; writing style is a separate presentation function supplied preferably by the standalone `writing-style` Skill.

## Core pipeline

`DISCOVER → OBSERVE → INTELLIGENCE → CLASSIFY → SELECT METHOD → ANALYZE → SYNTHESIZE → DECIDE → GOVERN → SELECT ARTIFACT → SELECT STYLE → RENDER → VALIDATE`

## Internal decision model

Maintain a single structured model containing at least:

- context
- problem
- goals
- non_goals
- constraints
- architecture_drivers
- current_state
- boundaries
- critical_flows
- observations
- evidence
- assumptions
- architecture_smells
- options
- reasoning_plan
- reasoning_results
- tradeoffs
- decision
- consequences
- risks
- principles
- rules
- applicable_rules
- checks
- violations
- exceptions
- compliance
- validation
- migration
- open_questions

## Reasoning rules

1. Select a method based on the problem and objective, not by habit.
2. A method must consume explicit inputs and produce inspectable outputs.
3. Methods organize evidence; they do not create evidence.
4. Unknown evidence must remain UNKNOWN rather than becoming invented scores or facts.
5. A matrix score requires a stated criterion and evidence or an explicitly marked expert judgment.
6. MECE is a heuristic for useful partitioning, not a proof that categories are mathematically exhaustive.
7. SCQA is primarily a synthesis and communication structure, not evidence for a decision.
8. A reasoning result is not automatically an architecture decision.
9. Contradictory evidence must be surfaced, not silently averaged away.
10. Every consequential conclusion should trace to evidence, assumptions, or an explicit decision rule.

## Method families

### Problem structuring
- SCQA
- MECE
- 5W1H
- Logic Tree

### Root cause and causality
- 5 Whys
- Causal Chain
- Fishbone-style cause categories

### Comparison and decision
- 2D Matrix
- Decision Matrix
- Cost-Benefit
- Risk Matrix
- Reversibility Analysis

### Prioritization
- Impact-Effort
- Pareto

### Uncertainty and future change
- Scenario Analysis
- Sensitivity Analysis

## Method selection

Use `reasoning/method-selection.md` and the machine-readable `reasoning/method-selection.schema.json` to construct a reasoning plan.

Typical mappings:

| Objective | Preferred methods |
|---|---|
| Clarify a vague problem | 5W1H → MECE → Logic Tree |
| Explain an architecture issue | SCQA → MECE |
| Find root cause | Causal Chain → 5 Whys |
| Compare alternatives | Decision Matrix + Risk Matrix |
| Prioritize technical debt | Impact-Effort + Pareto |
| Evaluate a boundary | MECE + Boundary Analysis + 2D Matrix |
| Assess migration | Cost-Benefit + Risk Matrix + Reversibility |
| Reason under uncertainty | Scenario + Sensitivity Analysis |

## Governance integration

Reasoning may propose or compare decisions. Governance evaluates an already-established principle/rule set.

`Architecture Diff → Applicable Rules → Evaluation → PASS / FAIL / WARN / UNKNOWN → Exception or Remediation → Governance Report`

Governance must not silently invent new rules from smells or reasoning results.

## Artifact generation

Generate architecture documents, ADRs, diagrams, reviews, migration plans, and governance reports from the same decision model. Do not maintain contradictory copies of the decision.

## Quality gates

Before finalizing:

- evidence traceability is present
- assumptions are separated from facts
- reasoning method is appropriate to the question
- calculations and scoring are reproducible
- uncertainty is visible
- options are comparable on stated criteria
- decision follows from analysis
- governance rules are explicit
- exceptions have expiry
- diagrams and prose agree
- no unsupported architecture claims are presented as facts


## Writing style integration

Architecture Writing v1.7 separates **reasoning quality** from **expression quality**. The architecture decision model remains the source of truth. A standalone `writing-style` Skill may be invoked after the decision is established to render ADRs, architecture documents, reviews, reports, migration plans, and technical articles.

### Style contract

1. Select style from artifact type, audience, purpose, and explicit user preference.
2. Treat style weights as behavioral tendencies, not literal sentence percentages.
3. Do not use author imitation as an internal correctness criterion; translate requested influences into abstract properties such as structure, calmness, skepticism, literary density, precision, and humanity.
4. Anti-AI processing is a presentation quality gate, not a reasoning method.
5. Never allow style editing to change facts, evidence, assumptions, scores, confidence, governance outcomes, constraints, risks, or decisions.
6. Any newly introduced factual claim must return to the decision model for validation.

### Recommended external dependency

Use the separate `writing-style` Skill when available. See `writing/style-contract.md` and `writing/workflows/render-artifact.md` for the integration contract and local fallback.

### Artifact-specific defaults

| Artifact | Profile | Priority |
|---|---|---|
| ADR / decision | architecture-decision | decision clarity, trade-offs, uncertainty |
| Architecture explanation | architecture-explanation | progressive disclosure, examples, precision |
| Review / governance report | architecture-governance | evidence, rules, outcome, traceability |

## v1.7 quality gates

In addition to v1.6 gates:

- selected writing profile is appropriate to artifact and audience
- style has not altered technical substance
- evidence confidence is preserved through rewriting
- Anti-AI cleanup removed mechanical phrasing without removing necessary structure
- skeptical language is backed by evidence or clearly marked as judgment
- summaries and headings remain traceable to the decision model
