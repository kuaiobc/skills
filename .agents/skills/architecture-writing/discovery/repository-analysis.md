# Repository Architecture Analysis

For an existing system, inspect in layers:

`Repository → Build → Modules → Packages → Dependencies → Frameworks → APIs → Persistence → Messaging → Configuration → Deployment → Runtime → Architecture Graph`

Record observations rather than prematurely labeling the architecture. Detect language/build systems, module boundaries, dependency direction, framework conventions, public interfaces, database access, messaging, scheduled jobs, external integrations, deployment units, and configuration sources.

Output:
- repository inventory
- module map
- dependency map
- integration inventory
- persistence inventory
- runtime/deployment inventory
- candidate architecture model
- evidence-backed assessment
- unknowns requiring validation
