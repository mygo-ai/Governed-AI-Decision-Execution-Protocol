# PHP-native Implementation

**PHP-native implementation foundation.** PHP is the application and control-plane runtime; models remain external or private inference endpoints. Runtime acceptance status is recorded in [Implementation status](../IMPLEMENTATION-STATUS.md).

## Technical foundation

| Component | Selected direction |
|---|---|
| Runtime | PHP 8.4 |
| Framework | Symfony 7.4 LTS |
| Persistence | MariaDB / InnoDB with explicit transactions |
| Data access | Doctrine DBAL and versioned migrations |
| Application shape | Modular monolith with a separately isolated execution broker |
| Long-running work | Supervised PHP CLI workers; durable DB jobs, leases and heartbeats |
| UI | Server-rendered PHP templates with progressive JavaScript |
| Artifacts | Private storage with immutable references and content digests |
| Dependency management | Composer lockfile and exact release manifest |

## Application modules

Identity, ContractRegistry, RunService, ActionPlanner, PolicyService, GrantService, BudgetService, JobScheduler, ExecutionBroker, Reconciler, VerificationService and OperationsUI have explicit responsibilities and permission boundaries.

State transitions use legal-transition checks and optimistic concurrency. The same transaction records the state change, associated event and necessary job/outbox entry. Model and external tool calls run outside database transactions.

The broker has a separate runtime identity and narrowly scoped authority. Agents propose actions; they do not receive protected target credentials or unrestricted database access. The verifier independently reads permitted output and cannot rewrite acceptance criteria.

## Management panel

The first panel includes authentication; runs and creation; run details with tasks/events; exact-action approval; execution and verification results; and blocked/unknown-effect review. Browser writes require CSRF protection and server-side authorization.

Approval presents the target, environment, operation, scope, material change, cost ceiling, expiry and rollback/recovery limitations. Recovery never exposes an unconditional retry-all operation for ambiguous mutations.

## Python and additional infrastructure

The PHP core operates without Python. Preserve prior Python source as a reference runtime and compatibility-test input. Add specialized workers only when a concrete adapter requires them.

Redis, Kafka, Kubernetes, vector storage and microservices are not required for the first slice. Additional operational complexity requires a documented need. Framework or architecture changes require a short decision record with affected invariants.

## Delivery evidence

A runtime release needs source, a checksum, migrations, a secret-free configuration example, installation and worker/broker runbooks, test results, known limitations and an architecture-to-code status matrix. Public documentation alone is not an installable release.
