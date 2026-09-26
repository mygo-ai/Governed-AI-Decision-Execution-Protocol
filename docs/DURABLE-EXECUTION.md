# Durable Execution

Long-running AI workflows should not be designed as one fragile HTTP request around an LLM.

The architecture should survive:

- process crashes;
- server restarts;
- model timeouts;
- provider outages;
- rate limits;
- human approval delays;
- tool failures;
- partial success;
- retries;
- multi-day workflows.

## Reliability patterns

Depending on deployment scale, implementations may use:

- durable state machines;
- event sourcing;
- checkpointing;
- materialized state;
- idempotency keys;
- leases;
- heartbeats;
- retry policies;
- exponential backoff;
- dead-letter queues;
- compensating actions;
- Saga-like patterns;
- replay;
- timeouts;
- cancellation;
- pause/resume;
- backpressure;
- concurrency limits;
- distributed locks only where justified.

## Duplicate protection

The protocol does not claim magical exactly-once distributed execution.

Instead it requires practical duplicate protection, idempotency where available, reconciliation and explicit recording of ambiguous external outcomes.
