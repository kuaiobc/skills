# Architecture Work Workflow

Use the smallest workflow that can answer the question, but do not skip decision-critical stages.

1. **Frame** — clarify context, stakeholders, problem, goals, non-goals.
2. **Discover** — gather requirements, constraints, repository/system evidence.
3. **Model** — establish entities, relationships, boundaries, flows, ownership.
4. **Assess** — identify gaps, smells, drivers, quality risks, change impact.
5. **Reason** — select and execute appropriate reasoning methods.
6. **Design** — generate alternatives and architecture tactics.
7. **Decide** — compare options, record a recommendation, and leave `human_decision` pending until a person selects.
8. **Validate** — test assumptions, quality attributes, operational behavior, and consistency.
9. **Communicate** — produce diagrams and audience-specific artifacts.
10. **Evolve** — define migration, rollback, transition states, and governance.

### Skip rules

A stage may be lightweight when it is irrelevant, but the reason for skipping it should be explicit. For example, a small local refactor may not need a full migration plan; a data ownership change usually does.

### Escalation rules

Escalate to deeper reasoning when there are competing quality attributes, irreversible choices, high uncertainty, cross-team boundaries, data migration, security/trust changes, or material cost/reliability consequences.
