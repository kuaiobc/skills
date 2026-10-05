# Fitness Functions

A fitness function is a repeatable measurable test of an architectural property.

Examples:
- no dependency cycles
- dependency direction remains acyclic
- no cross-domain database access
- public API compatibility
- required timeout/retry policy exists

Thresholds must come from policy or explicit decision; never invent numeric limits.
