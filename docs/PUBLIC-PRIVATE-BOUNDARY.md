# Public / Private Boundary

The public repository exists to prove architectural seriousness without exposing implementation assets that create security or commercial risk.

## PUBLIC

May include:

- architecture principles;
- high-level diagrams;
- lifecycle;
- role boundaries;
- contract names and public fields;
- evidence semantics;
- deployment patterns;
- sanitized examples;
- public security posture;
- commercial overview;
- roadmap.

## PUBLIC_INTERFACE_ONLY

May include interfaces and concepts without internals:

- policy evaluation shape;
- authorization grant shape;
- model adapter interface;
- tool capability manifest;
- event names;
- deployment interfaces.

## PRIVATE

Typically includes:

- proprietary prompts;
- internal orchestration logic;
- evaluator datasets;
- scoring internals;
- proprietary improvement logic;
- production source code unless contractually supplied.

## CUSTOMER_SPECIFIC

Examples:

- integrations;
- custom domain profiles;
- organization policy;
- internal knowledge mappings;
- private deployment topology.

## SECURITY_SENSITIVE

Must not be published merely to appear technically sophisticated:

- secret handling internals;
- production credentials;
- exploitable authorization details;
- private allowlists;
- deployment secrets;
- security-sensitive bypass logic;
- incident playbooks containing exploitable internals.
