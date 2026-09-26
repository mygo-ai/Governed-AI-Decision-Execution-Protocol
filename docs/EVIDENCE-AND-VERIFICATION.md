# Evidence and Independent Verification

The protocol separates evidence records, model opinions and real-world outcomes. The verifier independently reads permitted artifacts and checks frozen acceptance criteria.

## Evidence model

Material claims retain their provenance and classification: `FACT`, `DIRECT_OBSERVATION`, `EXTERNAL_EVIDENCE`, `VENDOR_CLAIM`, `MODEL_INFERENCE`, `ASSUMPTION`, `HYPOTHESIS` or `UNKNOWN`.

An evidence record identifies its source, collection method, scope, time, immutable artifact reference, digest and responsible identity. Relationships include supports, contradicts, derives from, supersedes, invalidates and confirms/fails acceptance.

Freshness, applicability and independence are assessed separately. A valid signature establishes origin and integrity, not factual correctness. A content hash detects changed bytes but does not protect against a privileged attacker rewriting both data and hash.

## Independent checks

An executor's `independent=true`, a model's statement of success or an unavailable source reference is not proof. Accepted checks need an authorized verifier identity, actual check execution, exact input references and attributable result evidence.

Execution status, verification status and outcome status remain distinct. Different models agreeing is not independent evidence unless their checks are independently grounded.

## Gate derivation and invalidation

A verification gate requires complete required coverage, valid matching artifacts, fresh evidence, the required independence and no unresolved critical blockers or revocation. Store the input digests and evidence/acceptance revisions with the gate.

New critical contradictions, changed acceptance criteria or revoked evidence invalidate dependent eligibility and undispatched grants. Dispatch and promotion recheck the gate revision transactionally; a cached task PASS cannot authorize stale work.

Verification eligibility is not production deployment permission. Production authority remains a separate policy/approval decision.

## Results

Checks distinguish `PASS`, `FAIL`, `NOT_RUN` and `BLOCKED`. Insufficient or unavailable evidence must remain `UNKNOWN` or `INSUFFICIENT_EVIDENCE` at the gate. An unperformed required check cannot silently become PASS.

The first milestone uses independent JSON/content verification and adversarial cases for tampered artifacts, fabricated receipts and late critical contradictions. See [First milestone](FIRST-MILESTONE.md).
