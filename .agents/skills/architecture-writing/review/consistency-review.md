# Consistency Review

Check that requirements, drivers, architecture model, diagrams, ADRs, migration plan, and governance rules agree.

Typical inconsistencies: diagram shows an event but design says synchronous call; ADR says service owns data but schema is shared; migration assumes zero downtime while deployment cannot support compatibility.
