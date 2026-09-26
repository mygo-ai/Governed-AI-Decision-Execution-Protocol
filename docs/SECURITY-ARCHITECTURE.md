# Security Architecture

Every model output may be incorrect. Every external content source may be adversarial.

## Identity

Important actions should be attributable across:

- human actor identity;
- workload identity;
- agent identity;
- model/provider identity;
- delegated authority.

## Authorization

A private implementation may combine:

- RBAC;
- ABAC;
- capability-based authorization;
- policy-as-code;
- per-action permissions;
- one-time action grants;
- TTL;
- nonce;
- environment scope;
- resource scope;
- tool scope.

## Tool security

The architecture must account for:

- indirect prompt injection;
- malicious files/webpages;
- poisoned repository instructions;
- untrusted API responses;
- parameter injection;
- shell injection;
- SSRF;
- secret leakage;
- unsafe file access;
- unauthorized network egress;
- privilege escalation.

Untrusted content must remain distinguishable from trusted system instructions.

## Secrets

Preferred patterns include:

- secret brokers;
- short-lived credentials;
- scoped credentials;
- secret references rather than plaintext;
- encrypted storage;
- customer-managed secrets;
- vault integration;
- rotation;
- audit.

## Isolation

High-risk tooling may require isolation for:

- shell;
- code execution;
- filesystem;
- browser;
- network;
- package installation;
- external connectors.

## High-risk action gates

Mandatory or stricter gates should be considered for:

- production writes;
- destructive actions;
- financial actions;
- contractual actions;
- credential use;
- customer-data export;
- security-sensitive changes;
- infrastructure changes;
- privilege changes.

## Multi-tenancy

Multi-tenant implementations should explicitly design:

- tenant isolation;
- tenant-specific policy;
- tenant-specific encryption;
- tenant-specific tools;
- model policy;
- retention;
- deletion;
- export.

Private single-tenant deployment remains a first-class option.
