# Delivery Roadmap

The engineering sequence is defined. Private implementation is nearing completion and component-level validation is confirmed by the project owner. This sequence organizes integration and release acceptance; it does not imply that every listed implementation task is still outstanding. Stages express delivery scope, not promised dates or existing runtime releases.

| Stage | Delivery | Exit evidence |
|---|---|---|
| **1. Baseline and containment** | Inspect the latest source, preserve compliant work, bind authorization to exact actions and invalidate stale verification gates | Current-source gap analysis and regressions for changed authorized inputs and late critical contradictions |
| **2. PHP transactional foundation** | PHP 8.4 / Symfony 7.4, MariaDB migrations, authenticated UI/API, contracts, state machine, jobs, outbox and budget ledger | Repeatable installation, legal transitions, atomic state/event/job writes and concurrent budget tests |
| **3. Governed sandbox cycle** | Isolated broker, actual file adapter, synthetic HTTP effect target, durable recovery, independent verifier and operational panel | Full sandbox acceptance including real isolation, parallel workers, crash injection and lost-response reconciliation |
| **4. Staging integration and evidence** | Provenance-bound checks, gate revisions and one explicitly scoped staging connector | Connector conformance, policy denial, receipt provenance and no stale gate consumption |
| **5. Private operations and pilot** | Approved model adapters, supervision, backups/restores, operational runbooks and customer-specific pilot | Restore drill, old-grant revocation, outage/recovery checks and pilot acceptance |
| **6. Governed improvement** | Outcome collection, candidate lessons, isolated evaluation, controlled promotion and rollback | Candidate cannot self-promote; failed evaluation preserves stable behavior |
| **7. Supported private edition** | Documented support envelope, certified profiles/connectors, compatibility and export procedures | All applicable acceptance gates, operational evidence and agreed support commitments |

## Integration and release objective

Stages 1-3 converge at the integrated sandbox milestone. Preserve already completed private components and use the latest implementation inventory to identify remaining work. A fake model is permitted for deterministic tests; real authorization, adapter effects, isolation and recovery evidence are required.

The PHP core must not require Python. Existing Python assets remain reference and compatibility inputs. The initial environment is single-tenant and private; tenant/project/resource scoping remains mandatory in contracts and access checks.

## Version discipline

Public documentation 1.1.0, architecture blueprint v1.0 and the private runtime version are separate identifiers. Historical v0.5.1/v0.6.0 suggestions are not instructions to overwrite or downgrade a newer source package. Select runtime versions after inspecting the current baseline.

## Scope gates

Production connectors follow the successful synthetic slice. Redis, Kafka, Kubernetes, a vector database and microservices are not prerequisites for the first milestone. Universal domain support, unrestricted shell execution and autonomous policy relaxation are outside its scope.

See [Implementation status](IMPLEMENTATION-STATUS.md) and [First milestone](docs/FIRST-MILESTONE.md).
