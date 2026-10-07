# Architecture Decision Example

**Problem:** synchronous dependency chain causes latency amplification.

**Driver:** p95 latency target and dependency failure isolation.

**Options:** keep synchronous chain; asynchronous boundary; aggregation/cache.

**Recommendation:** introduce asynchronous processing for non-critical downstream work while retaining synchronous validation for the user-critical path.

**Why:** improves failure isolation and latency predictability at the cost of eventual consistency and operational complexity.

**Human decision:** pending.

**Validation:** load test, dependency-failure test, event lag monitoring, reconciliation check.
