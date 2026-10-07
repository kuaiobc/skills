# Architecture Knowledge Model

The canonical model is the shared semantic layer used by discovery, intelligence, reasoning, design, diagrams, writing, review, migration, and governance.

## Entity groups

### Intent
- context
- stakeholders
- business drivers
- goals / non-goals
- requirements
- constraints
- assumptions
- compliance requirements

### Architecture
- system
- subsystem
- service
- module
- component
- interface
- data store
- event
- external system
- deployment unit
- trust boundary
- ownership

### Relationships
- dependency
- call
- event publication / subscription
- data flow
- ownership
- deployment
- trust relationship
- synchronization

### Decision
- architecture drivers
- options
- criteria
- trade-offs
- decision
- consequences
- risks
- validation
- migration

### Evidence
- observation
- evidence
- inference
- claim
- contradiction
- confidence
- freshness

## State discipline

`Observed` means directly established. `Inferred` means derived from evidence. `Assumed` means temporarily accepted. `Proposed` means a design choice. `Decided` means explicitly accepted. Never merge these states.

## Identity and traceability

Stable IDs should be assigned to major requirements, drivers, entities, evidence items, options, decisions, risks, validation actions, and migration units. References should use IDs rather than duplicated prose.

## Projection rule

Artifacts are projections:

`Knowledge Model → Design / Diagram / ADR / Review / Migration / Governance`

The model is the source of semantic truth; documents are presentation surfaces.
