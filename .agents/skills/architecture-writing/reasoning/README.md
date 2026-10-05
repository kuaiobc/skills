# Reasoning Engine

The Reasoning Engine converts an architecture question into a reproducible analysis plan.

`Question → Objective → Problem Type → Method Chain → Evidence → Analysis → Synthesis → Decision`

A method is an analytical operator. It has:

- purpose
- inputs
- procedure
- outputs
- failure modes
- evidence requirements
- composition rules

## Composition

Methods may be chained when outputs are compatible. Example:

`MECE → Logic Tree → Causal Chain → Decision Matrix → SCQA`

The last method may synthesize the result for humans; it must not alter the underlying evidence.
