# PHP-native Private Architecture

## What PHP-native means

PHP-native does not mean rewriting an AI model in PHP.

It means implementing the deterministic application, control plane and governance architecture naturally in a PHP environment.

## Variant A - PHP Native

```text
PHP Web UI
PHP API
PHP Control Plane
PHP Policy Enforcement Layer
MariaDB / MySQL
Queue / Worker System
Model Gateway
Tool Adapters
Audit / Evidence Storage
```

Suitable where a PHP-centric private deployment, familiar operations model and integrated web application are priorities.

## Variant B - PHP Control Plane + Specialized Workers

```text
PHP UI / API / Control Plane
MariaDB / MySQL
Queue
PHP Workers
Optional Python / Node Specialized Workers
Model Gateway
Execution Adapters
```

Another runtime is used only where it provides a material capability advantage.

## Variant C - Python Reference Runtime

A lightweight Python runtime can remain useful for:

- CLI;
- reference implementation;
- development;
- evaluation;
- specialized automation.

## Contract portability

The protocol contracts should remain language-neutral.

A `PlanContract` or `AuthorizationGrant` should not require redesign merely because the runtime language changes.

## Commercial availability

myGO offers PHP-native private implementation and integration engagements based on this protocol.

The exact framework, queue, storage, policy engine and integrations are selected according to deployment constraints rather than popularity alone.
