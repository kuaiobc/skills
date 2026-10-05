# Language Profiles

Language is a realization system, not a style dimension. Resolve it in this
order: explicit user request, applicable profile or preset, then inference
from input language, target audience/platform, existing document, and domain
convention. An explicit user language request takes precedence over inferred
language. If it conflicts with a hard target-platform language requirement,
surface the conflict and ask which requirement to follow; do not silently
override either one. Ask about other language choices only when they materially
affect the result and cannot be inferred.

Treat an inferred language as a default-level value. Any explicit language
setting from the user's request, context, profile, or preset takes precedence
over that inference.

Locale controls spelling and usage within a language. Keep domain terms in
their established form when translating them would reduce clarity. Language
and audience constrain realization; neither silently changes the requested
meaning or explicit style values.

Available profiles: `zh-CN`, `zh-TW`, `en-US`, and `en-GB`.
