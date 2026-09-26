# Sanitized Protocol Examples

These files illustrate public interface concepts. They are intentionally incomplete and do not expose private policies, prompts or evaluator rules. Placeholder references and digests cannot authorize an operation.

| Example | Purpose |
|---|---|
| [Objective](objective-contract.example.yaml) | Objective and constraints |
| [Plan](plan-contract.example.yaml) | Bounded tasks and stop conditions |
| [Action request](action-request.example.yaml) | Exact sandbox operation, resource and preconditions |
| [Authorization grant](authorization-grant.example.yaml) | Digest-bound scope and dispatch limits |
| [Evidence](evidence-record.example.yaml) | Provenance and claim relationships |
| [Verification report](critic-report.example.yaml) | Missing required evidence blocks eligibility |
| [Outcome](outcome-record.example.yaml) | Execution, verification and outcome stay separate |

The examples are independent explanatory fragments, not a complete executable workflow or production schemas. Status values in an example describe its hypothetical record, not a test result for the private product. The legacy `critic-report` filename is retained while illustrating the current `VerificationReport` contract.
