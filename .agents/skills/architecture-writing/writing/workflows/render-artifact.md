# Render Architecture Artifact

```text
Decision Model
  ↓
Artifact Type
  ↓
Writing Profile
  ↓
Style Preset
  ↓
Draft
  ↓
Anti-AI Pass
  ↓
Traceability Check
  ↓
Final Artifact
```

## Rules

- Render from the decision model; do not reconstruct decisions from prose.
- Select the minimum style intensity needed for the artifact and audience.
- Run Anti-AI cleanup after the factual draft exists.
- Re-check every consequential claim against evidence, assumptions, reasoning results, or explicit decision rules.
- If style editing introduces a new factual claim, stop and return it to the decision model for validation.
