# Composition Workflow

1. Parse task intent and explicit constraints.
2. Resolve language and locale, then audience, using explicit requests before
   context inference.
3. Collect profile, preset, dimension, anti-AI, and default sources with
   provenance, authority, and hard/strong/soft strength.
4. Normalize all inputs into Style IR.
5. Merge scalar, list, map, and behavior fields using `merge-rules.yaml`.
6. Compile dimensions into behavior candidates; apply interactions.
7. Resolve contradictions by hard constraints, user intent, task criticality,
   audience need, language correctness, authority, then style preference.
8. Record winning and suppressed behaviors and reasons.
9. Freeze Effective Style IR and Behavior IR before drafting.
10. Draft, evaluate, and rewrite using only the frozen effective model.

Unresolved conflicts that materially change user intent must be surfaced.
