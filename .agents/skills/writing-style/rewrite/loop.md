# Rewrite Loop

Pseudo-process:

```text
baseline = evaluate(draft)
best = draft
accepted = acceptance_gates_pass(baseline)
no_progress = false

for iteration in 1..max_iterations:
    if accepted or no_progress or stop_condition(baseline):
        break

    for round in 1..max_rewrite_rounds_per_iteration:
        batch = select_rewrite_batch(prioritize(baseline.issues))
        candidate = targeted_rewrite(draft, batch, behavior_ir, style_ir)
        candidate_eval = evaluate(candidate)

        if protected_dimensions_regressed(candidate_eval, baseline):
            reject(candidate)
            mark_regression(batch)
            continue

        if improvement(candidate_eval, baseline) < minimum_improvement:
            reject(candidate)
            no_progress = true
            break

        draft = candidate
        best = candidate
        baseline = candidate_eval
        accepted = acceptance_gates_pass(baseline)

        if accepted or stop_condition(baseline):
            break

return best, accepted, unresolved_material_issues(baseline)
```

## Rewrite principle

Do not rewrite to make the score move.

Rewrite to fix the observed problem.

The score is evidence that the fix worked, not the target itself.
Return a candidate as accepted only when every acceptance gate passes. The
rewrite budget bounds the work; it does not convert an unfinished candidate
into a passing result.
