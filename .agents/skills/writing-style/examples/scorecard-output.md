# Example Evaluation Output

```text
Task             95  PASS
Correctness      95  PASS
Logic            88  PASS
Audience         92  PASS
Language         90  PASS
Structure        84  PASS
Behavior         78  PASS
Style Fidelity   82  PASS
Anti-AI          86  PASS
Drift            12  PASS

Top issue:
Section 3 does not expose the operational trade-off implied by the
skeptical style configuration.

Recommended action:
Add one concrete cost and one boundary condition.

Rewrite scope:
Paragraph only.
```

The evaluator does not say "make it more human." It identifies an observable
behavior gap and a bounded rewrite.
