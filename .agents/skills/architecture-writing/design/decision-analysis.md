# Decision Analysis

Decision analysis compares options against architecture drivers and explicit criteria.

Use:

`Drivers → Criteria → Evidence → Option Scores/Assessment → Trade-offs → Recommendation → Human Decision`

## Rules

- derive criteria from actual drivers;
- explain weights when weights are used;
- distinguish measured evidence from expert judgment;
- show important uncertainty;
- run sensitivity analysis when rankings can change materially;
- show rejected or lower-ranked options and the reason;
- leave infeasible options visible and exclude them from the ranking;
- when feasible options tie, leave `recommended_option` empty and name the evidence, measurement, or weight judgment that would separate them;
- never turn a recommendation into a human decision automatically.

## Output fields

- `options`
- `criteria`
- `evidence`
- `tradeoffs`
- `recommended_option`
- `recommendation_rationale`
- `rejected_or_lower_ranked_options`
- `uncertainties`
- `human_decision`
- `decision_status`

`human_decision` may be empty or `pending` until a person decides. A tie is not resolved by picking the first option in the list, by preferring the newest technology, or by averaging scores the evidence cannot support. The output then contains the tied options, the comparison that failed to separate them, and the specific evidence that would.
