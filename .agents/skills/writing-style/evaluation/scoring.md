# Scoring Rules

Scores use 0-100. Higher is better except `drift_score`, where lower is
better.

`overall_score` is the weighted mean of the dimensions with a numeric weight
in `scorecard.yaml`. Normalize by the sum of weights for dimensions evaluated
in the selected mode. Keep the same evaluation mode when comparing a candidate
with its baseline. Improvement is the change in `overall_score`; issue
resolution and protected dimensions are separate acceptance checks. Do not
include `drift_score` in the aggregate. A missing score is not zero; report it
as not evaluated. Critical factual, task, or logic failures remain blocking
regardless of the aggregate.

Suggested interpretation:

```text
90–100 excellent
80–89 good
70–79 acceptable
60–69 weak
<60 problematic
```

These ranges are diagnostic.

Do not treat:
- 87 vs 88
- 72 vs 74

as objectively meaningful differences.

A score must be accompanied by evidence or issue descriptions when used for
decision-making.

## Protected dimensions

These cannot be compensated by style:

- factual correctness
- task completion
- logical correctness
- audience fit
- language fit
