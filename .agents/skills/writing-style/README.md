# Writing Style

A complete writing workflow for resolving language, audience, document type,
and style preferences into observable writing behaviors, then evaluating and
refining the result.

## Basic Usage

Choose a profile and preset, or give numeric style weights:

```text
profile=technical preset=technical-thinker
structure=70 tone=10 skepticism=20
```

Profiles are in `profiles/`; presets are in `config/presets.yaml` and
`presets/`. Numeric weights describe tendencies, not sentence ratios.

## Capabilities

- Language profiles for zh-CN, zh-TW, en-US, and en-GB
- Audience profiles for executive, engineer, product, general, and academic
- Six document profiles, style presets, and twelve interpretable dimensions
- Behavior compilation, composition, provenance, and conflict resolution
- Anti-AI guidance for translationese, Chinglish, and generic prose
- Multidimensional evaluation, behavior coverage, and drift detection
- Bounded targeted rewriting with regression protection
- Legacy calmness, directness, and narrative dimensions remain supported
- High-level handling of author-style requests without phrase imitation

The main workflow is:

```text
Request -> Analyze -> Select profile/preset -> Resolve context
        -> Compose writing model -> Outline -> Draft -> Refine/Critique
        -> Evaluate -> Targeted rewrite -> Regression check -> Final
```

See `examples/` for composition and evaluation examples.
