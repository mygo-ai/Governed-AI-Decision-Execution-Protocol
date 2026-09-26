# Model & Tool Abstraction

## Model Gateway

Critical architecture should not be bound to one vendor.

A model registry/gateway may represent:

```text
provider
model
capabilities
context_limits
reasoning_level
tool_support
structured_output_support
cost
latency
data_policy
region
availability
trust_classification
```

Decision, execution and verification roles may be independently configured.

Fallback routing must preserve tenant data classification and region policy. If no compliant provider is available, wait or block instead of sending data to an unauthorized endpoint.

## Execution adapters

The protocol does not hard-code a named executor as the architectural core.

An execution agent proposes typed actions; the isolated broker dispatches permitted adapters. “Astra” is a role name, not a mandatory provider. An adapter declares its idempotency, result-lookup, precondition and compensation semantics. Unknown effects follow connector-specific reconciliation.

## Tool capability manifests

Tools should be able to declare properties such as:

```text
tool_id
tool_class
operations
read_scope
write_scope
network_scope
data_classification
side_effect_level
destructive_capability
credential_requirement
approval_requirement
idempotency_support
rollback_support
cost_model
timeout
rate_limit
```

## Interoperability

MCP, A2A or other protocols may be supported as adapters where useful, but native adapters must remain possible and external protocols should not become unnecessary architectural dependencies.
