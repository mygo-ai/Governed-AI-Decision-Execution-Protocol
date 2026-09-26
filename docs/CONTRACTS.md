# Contract Architecture

The protocol uses versioned machine-readable artifacts to prevent critical operational state from existing only in prose.

## Candidate contract families

The public protocol may define or evolve artifacts such as:

| Artifact | Purpose |
|---|---|
| `RunIntake` | Initial request and run metadata |
| `ObjectiveContract` | Objective, constraints and success definition |
| `ContextSnapshot` | Context captured for a specific decision/run |
| `ConstraintContract` | Explicit limits and obligations |
| `ClaimRecord` | Material claim and epistemic type |
| `EvidenceRecord` | Evidence, provenance and verification metadata |
| `AssumptionRecord` | Explicit assumption |
| `DecisionRecord` | Decision and supporting references |
| `PlanContract` | Approved execution plan structure |
| `TaskContract` | Bounded executable task |
| `ToolCapabilityContract` | Tool capability declaration |
| `ActionRequest` | Requested side effect |
| `PolicyDecision` | Policy evaluation result |
| `AuthorizationGrant` | Scoped permission to act |
| `ExecutionRecord` | What actually executed |
| `TaskResult` | Task result and artifacts |
| `EscalationRecord` | Decision-changing fact or blocked condition |
| `CriticRequest` | Verification request |
| `CriticReport` | Independent verification result |
| `OutcomeRecord` | Real-world outcome |
| `LessonRecord` | Candidate lesson from observed outcome |
| `ImprovementCandidate` | Proposed system change |
| `EvaluationRun` | Isolated evaluation evidence |
| `PromotionDecision` | Candidate promotion/rejection |
| `ReleaseManifest` | Release provenance |
| `RollbackRecord` | Rollback event |

This is a protocol catalog, not a promise that every artifact remains separate in every implementation.

## Common fields

Important artifacts should consider:

```text
schema_version
artifact_id
run_id
project_id
tenant_id
parent_refs
created_at
creator_role
creator_version
content_hash
status
provenance
supersedes
validation_state
```

## Evolution

Breaking schema changes must not silently reinterpret historical runs.

Implementations should support explicit:

- schema versions;
- compatibility rules;
- migration rules;
- immutable historical references;
- supersession semantics.
