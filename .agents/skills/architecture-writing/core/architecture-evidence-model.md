# Architecture Evidence Model

Use the evidence chain:

`Source → Observation → Evidence → Inference → Claim → Decision`

## Evidence types

- direct repository evidence
- runtime / production evidence
- metric evidence
- documentation evidence
- user / business evidence
- external evidence
- expert judgment
- assumption
- derived inference

## Required metadata

`id, type, source, scope, timestamp, freshness, independence, confidence, content, supports, contradicts`

### Confidence

Confidence describes the strength of support, not the importance of a claim. A highly important claim can still have low confidence.

### Contradiction

Contradictory evidence remains visible. Record both sides, compare source quality/freshness/scope, and either resolve with new evidence or preserve uncertainty.
