# Example: Should a Service Be Split?

Question: should `order-service` be split into `order` and `pricing`?

Reasoning plan:

`MECE → Boundary Analysis → Change-Frequency × Ownership Matrix → Decision Matrix → Risk Matrix → SCQA`

Evidence:
- pricing code changes frequently independently: HIGH
- teams have separate ownership: HIGH
- shared transaction boundary exists: MEDIUM
- operational cost of another deployment: MEDIUM

The matrix is used to compare options, not to manufacture a numeric certainty. The final ADR records the evidence and unresolved questions.
