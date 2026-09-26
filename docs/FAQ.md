# FAQ

## What is being built?

A governed AI decision and execution platform with a PHP-native control plane, isolated tool broker, durable workers and independent verification. The owner confirms that the private implementation is nearing completion and components have been validated separately. This repository publishes its architecture and delivery scope.

## Is every capability already demonstrated?

The owner confirms component-level validation in the private development work. Integrated acceptance and production rollout remain separately recorded release decisions. See [Implementation status](../IMPLEMENTATION-STATUS.md).

## Is PHP optional?

PHP 8.4 with Symfony 7.4 and MariaDB is the selected foundation for this implementation. It manages application logic, state and authority; it does not implement the underlying AI model. The PHP core must work without Python.

## What remains from the earlier Python runtime?

Reference behavior, compatibility fixtures and evaluation assets. The latest private source must be inspected before deciding what to preserve or migrate; historical version numbers do not justify a downgrade.

## What is the first concrete result?

An authenticated sandbox run that writes a real artifact, recovers interrupted work and independently verifies output. A synthetic HTTP counter additionally demonstrates lost-response reconciliation without repeating the logical effect.

## Does the AI authorize itself?

No. Models propose actions. Deterministic software evaluates permissions and approvals; the isolated broker enforces authority at dispatch.

## Is Astra or a specific provider required?

No. Astra is an execution-role name in earlier materials. Model and execution interfaces are provider-neutral, subject to capability and data-policy checks.

## Is execution exactly once?

No general exactly-once guarantee is claimed. The protocol requires logical action identity, connector-specific duplicate protection and reconciliation. Unresolved external effects remain blocked for review.

## Can it run on-premises?

On-premises is a defined deployment path. A delivered installation must pass environment-specific acceptance, including approved model access, isolation and recovery.

## Can it improve itself?

The roadmap includes outcome-driven candidate improvements. Separate evaluation and promotion gates control stable changes; a learner cannot grant itself promotion authority.

## Is this an open-source runtime?

No. This repository contains public documentation and sanitized examples under its existing license. Private implementation and commercial delivery terms are agreed separately.
