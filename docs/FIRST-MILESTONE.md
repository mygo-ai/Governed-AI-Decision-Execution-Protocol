# Integration Milestone: Governed Sandbox Execution

**Delivery objective:** an installable PHP application that completes one authorized action cycle, recovers interrupted work and independently verifies output. Component-level validation is confirmed by the project owner. This document defines the integrated acceptance gate joining those components; the current status is recorded in [Implementation status](../IMPLEMENTATION-STATUS.md).

## End-to-end scope

Authenticated intake through UI/API; versioned contracts and semantic validation; deterministic policy; exact-action approval where required; a real isolated broker; durable workers; private artifacts; independent verification; and an operational review panel.

## Adapter 1: sandbox artifact writer

Create `output/report.json` containing `status=ready` in a registered workspace. Resolve the target from a server-controlled resource ID. Bind relative path, content digest and expected previous state to authorization.

Reject path traversal, absolute paths, symlink escapes, unauthorized resources and unsupported file types. Use conditional safe writes. Two concurrent creates expecting no previous file must produce one success and one precondition failure. A separate verifier reads the real output, checks its digest and parses its JSON content.

## Adapter 2: synthetic HTTP effect target

A local test service increments a counter with an idempotency key, returns an operation receipt, supports operation-ID lookup and can intentionally drop the response after applying the effect. The runtime must reconcile the lost response without incrementing the counter again for the same logical action.

## Required evidence

| Area | Acceptance requirement |
|---|---|
| Installation and database | PHP app installs; MariaDB migrations complete; authenticated run creation works |
| Happy path | Real sandbox bytes and a separate verifier receipt |
| Approval binding | Changed target/arguments, expired approval and revoked policy produce no target call |
| Worker races | Two actual processes compete; one valid dispatch commitment; stale writes rejected |
| Crash recovery | Controlled faults before dispatch and after effect preserve recoverable state |
| External ambiguity | Applied effect plus lost response reconciles without duplicate mutation |
| Isolation | Worker cannot directly reach protected target or use its credentials |
| Tenant/resource scope | Cross-scope action, artifact and resource access is rejected |
| Input and egress | Malformed/oversized input rejected; untrusted content cannot widen scope or exfiltrate data |
| Budget | Competing reservations cannot exceed the limit; uncertain cost remains accounted for |
| Cancellation | Before/after dispatch commitment behavior matches the documented boundary |
| Verification | Fabricated receipts, unavailable evidence and tampered artifacts cannot PASS |
| Gate freshness | New critical contradictions invalidate prior eligibility |
| Database retry | Deadlock recovery repeats only the transaction, never the effect |
| Historical import | Original references retained; old assertions do not become fresh verified evidence or grants |
| Operations UI | Approval and recovery controls are backed by server-side authorization |

Concurrency tests require separate processes with controlled synchronization. Fault injection uses named points. Sequential calls and policy mocks are insufficient evidence of those properties.

## Delivery package

Versioned source, SHA-256, changelog, migrations, configuration example without secrets, installation instructions, worker/broker runbooks, test report, limitations, implementation-status matrix, next-step checkpoint, and an English commit title/body.

Each runtime requirement maps to implementation files, test evidence, status and remaining work. Runtime test results use `PASS`, `FAIL`, `NOT_RUN` or `BLOCKED`; unavailable tests include a reason and a reproducible command.

## Completion verdict

`PASS_FOR_SANDBOX_SLICE`, `REWORK_REQUIRED`, `BLOCKED` or `INSUFFICIENT_EVIDENCE`.

Sandbox acceptance does not establish production readiness. Production services, real payments, customer messages and live infrastructure mutations are outside this milestone. They require separate integration and operational acceptance.
