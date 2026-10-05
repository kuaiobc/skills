# Governance Violation Example

Rule: domain modules must not directly access another domain's persistence layer.

Architecture diff: `checkout → customer-db` edge added.

Evidence: dependency graph and import path.

Result: FAIL / MAJOR.

Possible outcomes:
- remediate the dependency
- invoke an approved exception process

The violation does not itself decide which architectural remediation is best.
