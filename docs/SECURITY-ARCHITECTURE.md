# Security Architecture

Model output and external content are untrusted inputs. Deterministic validation and isolated execution enforce authority independently of the model's reasoning.

## Identities and privileges

Separate human operator, approver, agent, broker and verifier identities. The agent proposes actions and reads permitted artifacts; it cannot approve, consume grants or promote releases. The broker dispatches scoped adapters but cannot edit users, policies or acceptance. The verifier reads permitted output and issues attributable check records.

A single authenticated operator can fill the approver role for the initial sandbox scope. Stronger separation of duties is policy-driven; never simulate a second human identity.

## Execution perimeter

Protected credentials and outbound access are restricted to the broker. OS identities, filesystem permissions and network controls must prevent direct worker access. Server-controlled resource IDs resolve targets; arbitrary caller paths and unrestricted commands are not accepted substitutes.

Sandbox writes validate relative paths, symlinks, expected prior state and content digests. Tool adapters enforce typed operations, resource ownership, egress and data-classification rules. Calling a tool “read-only” does not authorize data export.

## Threats and controls

| Threat | Control and acceptance evidence |
|---|---|
| Changed action after approval | Immutable action digest and dispatch-time validation |
| Prompt injection or malicious content | Untrusted input classification and broker-enforced scope |
| Cross-tenant/project/resource access | Server-resolved identity, ownership and scoped queries |
| Stale worker or duplicate delivery | Leases, fences, logical keys and reconciliation |
| Forged verification | Authorized verifier receipts and independently read artifacts |
| Late critical contradiction | Gate revision invalidation and consumption-time recheck |
| Secret leakage or forbidden model fallback | Brokered secrets, restricted egress and uniform data policies |

## Operations

Use authenticated sessions, CSRF protection and server-side authorization for browser actions. Store secret references rather than values in model-visible contracts. Audit permission changes and keep sensitive telemetry scoped.

The initial deployment is private and single-tenant; tenant/project/resource scope remains explicit. Backup restoration requires recovery-safe startup and authorization revalidation before dispatch resumes.

Security claims require real runtime isolation and fault tests. Public architecture disclosure must not defeat the controls; security must not depend on hiding this design. The trusted broker and privileged host administrators remain explicit trust boundaries.
