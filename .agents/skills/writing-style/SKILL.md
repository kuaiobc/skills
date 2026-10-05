---
name: writing-style
description: A reusable writing-style engine for essays, technical documents, reports, blogs, proposals, notes, emails, and other long-form writing. Use it when the user asks to write, rewrite, polish, expand, shorten, or transform a document and wants a specific voice, structure, tone, or reduced AI-like feel. Style is controlled through composable profiles and numeric dimensions rather than imitation of a living author.
---

# Writing Style v1.0

## Purpose

This skill controls **how a document is written**, not what domain knowledge it contains. Keep it separate from domain skills such as architecture-writing, product-writing, or research-writing.

The engine combines:

1. Document Profile — what kind of document this is.
2. Style Preset — the desired writing direction.
3. Style Dimensions — continuous, interpretable style controls.
4. Anti-AI pass — removes mechanical and generic language without making prose artificially colloquial.
5. Critic pass — checks style, structure, clarity, and human judgment.

## Priority

When constraints conflict, use this order:

1. Factual correctness and user-provided facts
2. User's task and intended audience
3. Logical clarity
4. Appropriate document structure
5. Style consistency
6. Literary decoration

Never sacrifice meaning for style.

## Core Principle

Do not simulate a human by adding human-like filler. Simulate human thinking by making choices, trade-offs, observations, uncertainty, and judgments explicit when the source material supports them.

Never invent personal experience, observations, emotions, quotations, experiments, or facts merely to make writing feel human.

## Workflow

### 1. Identify the task

Determine:
- document type
- audience
- purpose
- desired length
- source material
- required structure
- explicit style instructions

If the user gives a numeric style such as `70/10/20`, map it to the active preset or ask only when the dimensions are genuinely ambiguous.

### 2. Load a Profile

Profiles define document-level constraints. See `profiles/`.

A profile answers: **What kind of document is this?**

### 3. Load or construct a Preset

Presets define the style mixture. See `presets/`.

A preset answers: **What should this document feel like?**

If the user supplies percentages, treat them as relative stylistic intensity, not sentence-level quotas.

### 4. Build a style model

Translate dimensions into observable writing behavior. Do not merely repeat dimension names in the prompt.

For example:
- high structure → explicit hierarchy and strong information progression
- high skepticism → challenge assumptions and expose boundary conditions
- high calmness → restrained vocabulary and low emotional volatility
- high humanity → concrete judgment and natural rhythm, not filler
- high literary → imagery and cadence used selectively

See `dimensions/`.

### 5. Draft for meaning first

Produce a structurally sound draft before applying literary or conversational effects.

Prefer:
- concrete nouns
- specific verbs
- examples
- explicit causal relationships
- stated trade-offs
- meaningful transitions

Avoid adding decorative language when it does not improve understanding.

### 6. Anti-AI pass

Run the draft through `anti-ai/`.

Remove or rewrite:
- generic openings
- empty conclusions
- formulaic transitions
- excessive symmetry
- repetitive bullet patterns
- abstract nouns without evidence
- buzzword stacking
- performative humility
- fake personal anecdotes
- unnecessary meta-commentary

Do not globally ban words. Judge them by function and repetition.

### 7. Critic pass

Run:
- `style-critic.md`
- `anti-ai-critic.md`
- `structure-critic.md`
- `final-critic.md`

Only rewrite passages that fail a criterion. Preserve strong original material.

## Style dimensions

The canonical schema is `config/style-schema.yaml`.

Default dimensions:
- structure
- tone
- skepticism
- humanity
- literary
- humor
- precision
- density
- persuasion

Dimensions use 0–100 intensity. They are **continuous tendencies**, not literal percentages of sentences.

## Author-style requests

When the user names an author, extract transferable attributes instead of attempting sentence-level imitation.

Use:
- structure
- rhythm
- degree of directness
- abstraction level
- skepticism
- warmth
- humor
- imagery
- information density

Do not reproduce distinctive passages or signature phrasing. For living authors, explicitly convert the request into high-level traits rather than direct imitation.

## Anti-AI philosophy

The goal is not to make prose messy. The goal is to remove signals of automated composition.

A sentence is not bad because it is polished. It is bad when it is polished **without carrying a useful observation, argument, fact, or transition**.

A transition is not bad because it says “因此”. It is bad when it merely announces that the writer is moving to the next paragraph.

A list is not bad because it is a list. It is bad when every idea has been forced into the same syntactic mold.

## Output behavior

Unless the user asks for the internal analysis, output the finished document rather than the style audit.

If useful, briefly state the active profile/preset before the document, but do not expose hidden chain-of-thought.
