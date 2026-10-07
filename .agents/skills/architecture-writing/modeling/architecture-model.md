# Architecture Model

Represent architecture explicitly instead of relying only on prose. Minimum entity vocabulary:

`System, Service, Module, Component, Interface, DataStore, Event, ExternalSystem, DeploymentUnit, TrustBoundary, Owner`

Minimum relation vocabulary:

`depends_on, calls, publishes, subscribes, reads, writes, owns, deploys_with, trusts, crosses_boundary`

Each entity should have a stable ID, name, responsibility, owner, lifecycle, and evidence source where applicable.
