# Policy Engine

Evaluation flow:

`Candidate Change → Rule Selection → Evidence Collection → Predicate Evaluation → Result`

Results:
- PASS
- FAIL
- WARN
- UNKNOWN
- EXEMPT

Default behavior should be read-only. The engine reports; it does not modify application code.
