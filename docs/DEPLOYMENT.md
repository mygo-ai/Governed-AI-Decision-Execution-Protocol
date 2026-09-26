# Deployment Models

Private deployment is a first-class architectural requirement.

## Supported target patterns

### Dedicated VPS

Good for bounded private deployments with modest operational complexity.

### Dedicated Server

Useful where hardware isolation, predictable resources or local control is required.

### Private Cloud

Suitable for enterprise network segmentation, internal identity and controlled data locality.

### On-Premises

For organizations that require infrastructure ownership, local trust boundaries or restricted data movement.

### Restricted / Air-Gapped

Possible where practical, subject to approved model and package availability.

### Single-Tenant Enterprise

Dedicated control plane, policies, secrets, storage and connectors.

### Hybrid

Private control plane with selected external model providers or approved external services.

## Deployment design questions

Every deployment should explicitly define:

- trust boundary;
- data location;
- model location;
- secret ownership;
- outbound network requirements;
- upgrade strategy;
- audit strategy;
- backup;
- restore;
- disaster recovery;
- provider failover.

## No mandatory myGO-hosted SaaS dependency

A private deployment should not require a myGO-hosted SaaS control plane unless the customer explicitly chooses such a model.
