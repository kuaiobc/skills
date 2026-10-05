---
name: writing-style
description: >
  Use when writing, rewriting, polishing, expanding, shortening, or transforming
  a document and the user wants control over voice, structure, tone, language,
  audience, or naturalness. Also use to evaluate or improve an existing draft.
  Domain facts must come from the request or an applicable domain skill.
---

# Writing Style

Resolve a writing request into one effective style model, draft from it, and
review the result at the depth the user requested:

```text
Analyze -> Select profile/preset -> Resolve language/audience -> Compose
        -> Compile behaviors -> Outline -> Draft -> Refine/Critique
        -> Evaluate when needed -> Targeted rewrite when requested -> Final
```

## Resolve the Request

1. Analyze purpose, deliverable, audience, source material, and constraints
   with `workflows/analyze.md`.
2. Choose one primary document profile from `profiles/`, registered in
   `config/profiles.yaml`. Select by deliverable and purpose, not topic alone.
   For example, a technical blog uses `blog` with an engineering audience;
   a technical decision document uses `technical`.
3. Resolve language and audience independently. An explicit user language
   requirement wins over inferred language. If it conflicts with a hard target-
   platform language requirement, surface the conflict and ask which to follow;
   do not silently override either requirement.
4. Select a preset from `config/presets.yaml` or `presets/`. A preset file may
   inherit a base preset, then override its named dimensions. The shorthand
   `70/10/20` means structure/tone/skepticism and uses
   `presets/70-10-20.yaml`.
5. Compose inputs into Style IR and compile the selected dimensions into
   observable behaviors. Follow `composition/` and `behavior-engine/`.

Profiles describe document-purpose constraints; presets describe stylistic
preferences. Profile bounds are strong by default. An explicit user style value
overrides a profile bound and records the conflict; hard task constraints
remain protected. Do not stack profiles unless the user requests a hybrid.

The dimensions in `config/style-schema.yaml` include the core style controls
and the legacy `calmness`, `directness`, and `narrative` controls. Values from
0 to 100 express intensity, not sentence quotas. When asked to write like an
author, use transferable high-level traits; do not imitate signature phrasing
or reproduce passages. Never invent facts or personal experience.

## Write and Refine

Use the task-appropriate procedures in this order:

1. `workflows/outline.md` for structure.
2. `workflows/draft.md` for drafting.
3. `anti-ai/` and `workflows/refine.md` for naturalness and voice.
4. `workflows/critique.md` and applicable files in `critics/` for review.

Factual correctness, task completion, and logical correctness outrank style.
Do not damage them to increase style fidelity or anti-AI scores.

## Evaluate and Improve

Evaluation depth changes review detail, not the requested deliverable. For an
evaluation-only request, return a scorecard and actionable issues without
rewriting. For an improvement request, run the evaluation and bounded rewrite
loop when `rewrite.enabled` is true. Fast evaluation remains available for
improvement requests and checks the same fast dimensions after each rewrite.

Use `evaluation/evaluator.md` and `evaluation/scoring.md` for score semantics;
`evaluation/issue-schema.yaml` and `evaluation/behavior-coverage.yaml` define
the diagnostic records. Use `rewrite/policy.yaml`, `rewrite/regression.yaml`,
and `rewrite/stop-criteria.md` for rewrite selection, protection, and
acceptance. Stopping because a budget ran out does not mean the draft passed.

## Output

- For a writing request, return the requested writing.
- For an evaluation request, return the scorecard and ranked, evidence-based
  issues.
- For an improvement request, return the improved writing and briefly note
  material changes when useful.
- Keep configuration and scoring details internal unless the user asks for
  them.
