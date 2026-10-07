# Technical Writing

This skill includes a minimum writing method so it remains usable without another writing skill. The method changes how the architecture model is read. It does not change what the model contains.

- State context, problem, and the recommendation early.
- State `human_decision` only when a person has confirmed, rejected, or modified the recommendation. Until then, write it as `pending`.
- Explain requirements, constraints, and drivers before solutions.
- Use short causal paragraphs: name the mechanism, then its consequence.
- Separate fact, assumption, inference, recommendation, and human decision. Do not let one sentence slide from one of these into another.
- Prefer concrete mechanisms and measurable claims. A quality claim names the scenario and the target already in the model.
- Use tables for comparisons and diagrams for relationships.
- Name risks, unknowns, and validation actions.
- Remove repetition, hype, and unexplained acronyms.

## Substance boundary

Rewriting may change order, sentence rhythm, headings, directness, and how much is explained. An example or transition may be added only when the model already contains the fact it illustrates.

Rewriting must not change:

- facts, evidence, or the source and scope of that evidence;
- numerical values, scores, weights, and confidence;
- constraints, risks, and exception status;
- governance outcomes, including `PASS`, `FAIL`, `WARN`, `UNKNOWN`, and `EXEMPT`;
- `recommended_option` and `human_decision`;
- which option a person selected.

Wording confidence follows evidence confidence. A cleaner sentence does not raise a `MEDIUM` or `LOW` inference to a fact. `UNKNOWN` stays unknown; it is not rewritten as a likelihood. If the model marks a score as expert judgment, the prose says it is judgment.

A metaphor may restate a relationship the model already records. It cannot supply a mechanism, a measurement, a cause, or a reason to prefer an option. Skeptical tone is not a finding. A challenge to an assumption must point to evidence, a contradiction already in the model, or a judgment labeled as judgment.

Headings, summaries, and closing sentences are claims. They may compress the model. They may not add a driver, a risk, a recommendation, a human decision, or a governance result that the model does not contain. If a rewrite needs a new factual claim, stop and return that claim to the decision model for validation before the document is treated as finished.

## writing-style integration

If a `writing-style` skill is available, use it for tone, language habits, and removal of mechanical phrasing. The substance boundary still applies. Architecture semantics, evidence, scores, governance outcomes, the recommendation, and `human_decision` stay owned by this skill.
