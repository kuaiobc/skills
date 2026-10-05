# Stop Criteria

Stop attempting rewrites when any stop condition is true:

1. the configured iteration or rewrite-round budget is exhausted
2. improvement is below the configured minimum
3. another rewrite would mostly be cosmetic
4. a candidate causes a protected regression and no safe candidate remains

Stopping does not automatically mean acceptance. Accept only when every
configured gate passes: no critical or high issues, overall score at or above
target, behavior coverage at or above minimum, drift at or below maximum, and
no protected dimension regression. If the budget ends before those gates pass,
return the best non-regressed draft and report the remaining material issues.
