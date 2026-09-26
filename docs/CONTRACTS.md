# Contract Architecture

Versioned machine-readable artifacts connect reasoning, authority, execution and verification. Schema validity is necessary; semantic checks establish correct ownership, scope, operation, environment and dependencies.

## Core execution cycle

| Contract | Responsibility |
|---|---|
| `RunIntake` | Objective, request identity and initial constraints |
| `PlanContract` | Bounded tasks, dependencies and approved plan references |
| `TaskContract` | A task's scope, resources and execution limits |
| `AcceptanceSpec` | Frozen criteria and required check/evidence definitions |
| `ActionRequest` | Exact proposed target, operation, typed arguments and preconditions |
| `PolicyDecision` | Software-derived permission decision and approval obligations |
| `AuthorizationGrant` | Narrow, expiring authority bound to the canonical action digest |
| `ExecutionRecord` | Actual attempt, adapter, fence, effect state and receipt |
| `TaskResult` | Output references and separate execution/result state |
| `VerificationReport` | Independent checks, evidence revisions and acceptance verdict |

Broader contract families include `ObjectiveContract`, `ContextSnapshot`, `ClaimRecord`, `EvidenceRecord`, `DecisionRecord`, `ToolManifest`, `OutcomeRecord`, `LessonRecord`, `ImprovementCandidate`, `EvaluationRun`, `PromotionDecision`, `ReleaseManifest` and `RollbackRecord`.

Earlier materials use `CriticReport` for the broader review aggregate and `ToolCapabilityContract` for tool capability descriptions. Compatibility must be explicit; do not silently reinterpret historical fields or imply that every family needs a separate database table.

## Identity and immutable references

Common envelope concepts include schema version, artifact ID, tenant/project/run identity, creator identity/version, creation time, parent references, content digest, provenance and supersession. Artifact references resolve to immutable bytes within the caller's permitted scope.

Canonicalization rejects malformed input and ambiguous representations, including duplicate JSON keys, before an authorization digest is accepted. Hashes must identify exact material inputs, not a mutable path that may later contain different data.

## Action binding

Approval and grants bind the target, operation, tool/version, typed arguments, environment, credential scope, side-effect classification, relevant task/plan/policy/acceptance references and budget limits. Any material change requires re-evaluation. Server-controlled tool metadata determines risk; the model cannot downgrade its own action.

The same logical key with different action content is a conflict. The broker consumes the initial grant atomically and checks current policy, cancellation, scope and resource preconditions. Recovery attempts retain the logical operation's identity and require current authorization.

## Historical compatibility

Breaking changes create a new schema version and explicit migration. Preserve original bytes, digests and trust classifications. Historical operator assertions do not become independent verification, and old approvals do not become fresh dispatch authority.

The [examples](../examples/README.md) are sanitized explanatory artifacts, not executable grants or a complete schema distribution.
