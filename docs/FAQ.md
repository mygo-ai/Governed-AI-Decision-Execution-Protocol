# FAQ

## Is this open source?

No. This repository is public documentation and architecture material. The private runtime and proprietary implementation are not distributed as open-source software here.

## Is this just a set of prompts?

No. The target protocol defines deterministic state, typed contracts, policy enforcement, scoped authorization, durable execution, evidence provenance, independent verification, outcome feedback and governed promotion/rollback.

## Does the AI decide whether it is allowed to act?

No. The architecture separates model reasoning from software authority.

## Is PHP supported?

Yes as a private implementation architecture. PHP-native refers to the deterministic application/control plane, not to implementing the AI model itself in PHP.

## Can Python still be used?

Yes. Python can remain a reference runtime or specialized worker where it provides a real capability advantage.

## Is the system tied to one model vendor?

No. The protocol is designed around a provider-neutral Model Gateway.

## Can it run on-premises?

The architecture is designed to support on-premises and other private deployment models, subject to implementation scope and external model availability.

## Does a successful execution mean the business outcome succeeded?

No. Execution success, verification success and real-world outcome are separate states.

## Does the system autonomously rewrite itself?

Not directly. Improvement candidates should pass evaluation, regression, adversarial review, policy/human gates and controlled promotion.

## Is every feature described here already implemented?

No such claim is made by this public repository. It is an architecture/protocol specification and commercial showcase. Implementation status depends on the private deployment/version.
