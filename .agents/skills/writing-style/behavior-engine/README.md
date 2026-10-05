# Dimension Behavior Engine

Weights are intensity signals, never sentence ratios. Compile a weight into
task-relevant observable behaviors, filter for profile/language/audience, apply
interaction rules, then emit a small set of constraints and checks.

Bands: 0-19 minimal, 20-39 light, 40-59 moderate, 60-79 strong, 80-100
dominant. A band proposes candidate behaviors; it does not force every
candidate into every document. The task and higher-priority constraints win.

The normative behavior catalog and interaction rules are in `behavior-map.yaml`
and `interactions.yaml`; the algorithm is in `compiler.md`.
