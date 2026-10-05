# Writing Layer Integration

Architecture Writing v1.7 treats writing style as a presentation layer, not as an architecture-reasoning mechanism.

The preferred dependency is the separate `writing-style` Skill. This skill consumes the architecture decision model and asks `writing-style` to render the selected artifact according to a profile and style preset.

## Separation of concerns

- Architecture Writing decides **what is true, what is inferred, what was analyzed, what was decided, and what must be governed**.
- Writing Style decides **how that material should be expressed**.
- Anti-AI checks operate on the rendered prose and must never alter facts, evidence, scores, decisions, rules, or constraints.

## Fallback

If `writing-style` is unavailable, use the local minimal rules in `writing/fallback-style.md`.
