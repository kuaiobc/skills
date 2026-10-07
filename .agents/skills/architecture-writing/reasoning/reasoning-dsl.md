# Reasoning DSL

A reasoning plan is a declarative execution graph.

```yaml
problem: boundary-selection
objective: choose a service boundary
inputs: [architecture-model, ownership-evidence, change-history]
steps:
  - id: partition
    method: MECE
    purpose: partition boundary concerns
    inputs: [architecture-model]
    outputs: [boundary_dimensions]
  - id: compare
    method: DecisionMatrix
    depends_on: [partition]
    inputs: [boundary_dimensions, ownership-evidence, change-history]
    outputs: [ranked_options]
    guards: [all_options_have_evidence]
stop_conditions:
  - decision_critical_unknown
```

The DSL is data, not prose. Runtime semantics are defined by the planner/executor contracts.
