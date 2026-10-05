# Behavior Compiler

Input: Effective Style IR, profile, resolved language and audience, preset,
task intent, and dimension weights.

1. Map each weight to its configured band.
2. Select behaviors that serve the document goal.
3. Filter behaviors that conflict with hard constraints or audience/language
   requirements.
4. Apply dimension interactions and precedence rules.
5. Assign each surviving behavior a task-relative priority (high, medium, or
   low) based on task criticality, constraint strength, and usefulness; do not
   derive priority from style weight alone.
6. Emit each behavior with an ID, intensity, priority, source, authority,
   status, writing constraint, and observable validation check.
7. Retain provenance through composition and evaluation.

Priority is high when omission would harm task correctness, a hard requirement,
or a central decision; medium when it materially improves the requested
document; low when it is an optional stylistic tendency.

Do not turn a weight into a frequency rule. For example, skepticism 20 means
selective examination of important assumptions, not one challenge every five
paragraphs. The result is a concise, testable Behavior IR.
