# Architecture Option Generation

Architecture design exposes structurally different choices before it recommends one. The list is an input to comparison and to the person who will decide. It is not itself a decision.

## Coverage

A list is complete when every structurally distinct response supported by the analysis is visible, including responses that should not be chosen.

1. Record the current state as one option. State the boundaries, data ownership, interaction style, and deployment it keeps, and which findings it leaves unchanged. Keeping the current architecture is a real choice, because the cost and risk of change are part of the comparison.
2. Take further options from structural dimensions the analysis made decision-critical. Typical dimensions are boundary, data ownership, interaction style, deployment, consistency, and failure isolation. Omit a dimension the analysis did not raise. Do not invent a finding, a constraint, or a score to justify an extra option.
3. Compose each option as one coherent set of positions on those dimensions. Include combinations the findings put in tension, not only the combinations that are locally convenient.
4. For a consequential decision, prefer three kinds of option when the problem allows them: the current state or simplest viable architecture, a balanced option, and one alternative with a different architectural trade-off.
5. Keep an option that breaks a known hard constraint. Mark it `infeasible` and name the constraint it breaks. A person should be able to see why it was not ranked. Removing it makes the list look smaller and hides a choice someone may still propose.
6. Drop an option only when its structural commitments duplicate another option. Record the dropped name. Replacing a library or product name while the structure stays the same is a duplicate, not a new architecture.
7. Stop when every decision-critical position appears in at least one option and any further combination only renames an existing option. Record that completeness check.

For each option record:

- id and name;
- structure and responsibilities;
- dependencies and data ownership;
- runtime behavior and failure behavior;
- security and trust implications;
- deployment and operations;
- migration path and reversibility;
- findings it answers and findings it leaves unchanged;
- unknowns it still depends on;
- key risks and assumptions;
- feasibility: `feasible`, or `infeasible` with the constraint it breaks.

## Recommendation

Compare feasible options with the comparison methods already selected. Infeasible options stay in the list and stay out of the ranking.

Set `recommended_option` only when one feasible option ranks first under the criteria, weights, and evidence actually used. In `recommendation_rationale`, state the hard filters, the criteria and weights, the options set aside and why, and which assumption or weight change would replace the recommendation.

When two or more feasible options remain tied, leave `recommended_option` empty. Name the tied options and the missing evidence, measurement, or weight judgment that would separate them. Do not invent a tie-breaker the analysis did not supply. A forced winner is a hidden decision.

The recommendation is not `human_decision`. The responsible person confirms, rejects, or modifies it. If that person selects an infeasible option, record the selection and keep the broken constraint beside it.
