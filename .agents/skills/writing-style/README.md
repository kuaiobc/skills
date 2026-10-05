# writing-style v1.0

A reusable writing-style engine for multiple document types.

## Basic usage

Choose a Profile and a Preset:

`profile=technical preset=technical-thinker`

Or use a numeric recipe:

`structure=70 tone=10 skepticism=20`

The numbers are stylistic weights, not literal sentence ratios.

## First preset

`presets/70-10-20.yaml` is the initial technical-thinker recipe: strong structure, restrained/plain tone, and deliberate skepticism. It is intentionally expressed as behavioral dimensions rather than author imitation.

## Design principle

Separate **what to write** from **how to write it**. Domain skills supply content and document-specific methodology; this skill supplies style and editorial quality control.
