# Deployment Architecture

**Initial target: single-tenant, private and self-hosted.** Deployment modes are defined architectural paths, with operational acceptance required for each delivered environment.

| Mode | Scope and condition |
|---|---|
| Dedicated VPS or server | Bounded private workload with enforced broker/worker isolation |
| Private cloud | Customer-controlled network, identity and storage boundaries |
| On-premises | Customer infrastructure with approved model and package access |
| Hybrid | Private control plane with explicitly approved external model endpoints |
| Restricted network | Requires compatible local/approved endpoints and dependency delivery; offline capability is not presumed |

## Runtime boundaries

PHP UI/API, supervised PHP workers, MariaDB and private artifact storage form the application foundation. The broker uses a separate identity/process or container with narrow credentials and egress. Model workers cannot directly access protected targets. Verifier access is separately scoped.

The architecture has no mandatory myGO-hosted SaaS control-plane dependency. Approved external model use still creates network and data-policy requirements.

## Acceptance obligations

An installation must establish authentication, permissions, filesystem/network isolation, secret references, logging, process supervision, database migration, backup/restore, artifact retention, recovery and upgrade procedures.

Restored environments start in a recovery-safe mode. Old grants must be revoked or revalidated before dispatch resumes. Target reconciliation protects against replaying effects that occurred after the restored checkpoint.

Production operation follows the sandbox slice, staging connector checks, restore drills and a scoped pilot. The runtime must publish its supported profiles/connectors and limits. See [Roadmap](../ROADMAP.md).
