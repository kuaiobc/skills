# Architecture Decision Model

A decision record keeps recommendation and human choice separate.

`Problem → Drivers → Criteria → Options → Evidence → Trade-offs → Recommendation → Human Decision → Consequences → Risks → Validation`

## Fields

- decision_id
- status: proposed / accepted / rejected / superseded
- scope
- problem
- drivers
- criteria
- options
- evidence
- tradeoffs
- recommended_option
- recommendation_rationale
- rejected_options
- human_decision
- decision_owner
- consequences
- risks
- assumptions
- validation_actions
- date
- supersedes / superseded_by

## Rule

The agent may produce `recommended_option`. It must not populate `human_decision` as if a person had approved it. If no human decision exists, use `pending` or leave the field explicitly unresolved.
