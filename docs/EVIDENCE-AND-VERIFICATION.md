# Evidence & Verification

## Evidence is not a list of URLs

The protocol models evidence as attributable records connected to claims and decisions.

Potential relationships include:

```text
SUPPORTS
CONTRADICTS
DERIVED_FROM
OBSERVED_BY
TESTED_BY
SUPERSEDES
DEPENDS_ON
INVALIDATES
CONFIRMS_ACCEPTANCE
FAILS_ACCEPTANCE
```

## Epistemic classes

Important claims should distinguish between:

```text
FACT
DIRECT_OBSERVATION
EXTERNAL_EVIDENCE
VENDOR_CLAIM
MODEL_INFERENCE
ASSUMPTION
HYPOTHESIS
UNKNOWN
```

## Evidence dimensions

Evidence assessment may consider:

- provenance;
- freshness;
- independence;
- applicability;
- contradiction;
- source quality;
- verification status;
- expiration;
- decision consequence.

## Critic verdicts

A verifier may emit:

```text
PASS
PASS_WITH_REVISIONS
REWORK
BLOCK
INSUFFICIENT_EVIDENCE
UNKNOWN
```

A test that could not be performed must not silently become PASS.

## Verification diversity

For high-risk tasks, verification may combine:

- deterministic checks;
- independent test execution;
- independent tool inspection;
- model-assisted review;
- a different model or provider when useful.

Different model opinions are not independent evidence unless they are independently grounded.

## Decision lineage

The target architecture should make it possible to answer:

> Why did the system believe this when the decision was made?

and:

> What new evidence caused the belief to change?
