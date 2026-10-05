# Rewrite Loop

The rewrite loop is:

```text
Evaluate
  ↓
Rank issues
  ↓
Select rewrite batch
  ↓
Rewrite smallest useful scope
  ↓
Regression check
  ↓
Re-evaluate
  ↓
Accept / Reject / Continue
```

The loop is bounded and regression-protected.
