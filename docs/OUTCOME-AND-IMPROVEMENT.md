# Outcome and Governed Improvement

Execution, verification and real-world outcome are three independent states. A successful tool call can fail acceptance; a verified implementation can still miss its business objective.

## Outcome records

Capture the intended metric, observation window, baseline, observed result, evidence and uncertainty. Preserve attribution limits: a later improvement does not by itself establish that the AI-generated change caused it.

## Controlled improvement

```mermaid
flowchart TD
    O[Observed outcome] --> L[Candidate lesson]
    L --> C[Candidate change]
    C --> E[Isolated evaluation]
    E -->|Fails or lacks evidence| R[Reject or rework]
    E -->|Meets criteria| G[Policy and promotion gate]
    G --> S[Staging or canary]
    S -->|Accepted| P[Stable release]
    S -->|Regression| B[Rollback]
    P --> O
```

Evaluation includes regression, adversarial and cost/latency checks. Learner identity cannot edit the evaluation authority or directly promote stable behavior. Promotion binds the candidate, evaluated artifacts, policy and evidence revisions; changed evidence invalidates stale eligibility.

Failed candidates leave stable behavior unchanged. Rollback and compensation limits must reflect the actual target's capabilities. Outcome-driven improvement has its own acceptance stage in the [Roadmap](../ROADMAP.md), separate from sandbox execution acceptance.
