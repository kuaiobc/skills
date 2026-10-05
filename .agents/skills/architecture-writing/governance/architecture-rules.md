# Architecture Rules

Rules turn principles into testable conditions.

A rule should define:
- id
- principle_id
- scope
- predicate
- evidence_source
- severity
- enforcement
- exception_policy

Example: `domain modules must not access another domain's persistence layer directly`.
