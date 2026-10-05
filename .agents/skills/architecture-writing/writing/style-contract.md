# Writing Style Contract

## Input

The writing layer receives a structured artifact model containing, where applicable:

- audience
- purpose
- artifact_type
- context
- problem
- goals / non_goals
- constraints
- architecture_drivers
- evidence
- assumptions
- unknowns
- observations
- options
- reasoning_results
- tradeoffs
- decision
- consequences
- risks
- principles / rules
- exceptions
- migration
- validation
- open_questions

## Output

The writing layer returns a document whose claims remain traceable to the input model.

Style transformations may change:

- ordering for readability
- sentence rhythm
- headings
- examples and transitions, when supported by the model
- degree of directness
- amount of explanation

Style transformations must not change:

- facts
- evidence
- numerical values
- decision criteria
- scores
- confidence
- governance outcomes
- constraints
- risks
- exception status

## Default style selection

1. Use an explicitly supplied `writing-style` profile/preset.
2. Otherwise select a profile by artifact type.
3. If no profile is available, use the local fallback rules.

## Style is not evidence

A more confident or elegant sentence must never increase evidence confidence. A skeptical tone must not manufacture counter-evidence. A literary metaphor must never be used as technical evidence.
