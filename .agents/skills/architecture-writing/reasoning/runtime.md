# Architecture Reasoning Runtime

The Runtime is the execution layer for reasoning plans.

States:
`DRAFT → READY → RUNNING → COMPLETED | COMPLETED_WITH_UNKNOWN | BLOCKED | FAILED`

Runtime invariants:
1. steps consume registered evidence or declared upstream results;
2. methods cannot create factual evidence;
3. derived claims retain lineage;
4. UNKNOWN remains explicit;
5. low-confidence results cannot silently become high-confidence decisions;
6. contradiction checks run where required;
7. sensitivity runs when configured and feasible;
8. deterministic inputs/config/method versions should reproduce results.

The Runtime never bypasses the architecture knowledge model.
