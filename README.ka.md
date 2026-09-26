# myGO Governed AI Decision & Execution Protocol

> **Probabilistic AI reasoning-ის გარდაქმნა governed, durable, auditable და verifiable execution-ად.**

**Models reason. Software controls state and authority.**

## რას წარმოადგენს პროექტი

**myGO Governed AI Decision & Execution Protocol** არის production-oriented არქიტექტურული protocol, რომელიც AI reasoning-ს აშორებს პირდაპირ execution authority-ს.

მისი ძირითადი იდეაა:

- AI აანალიზებს, მსჯელობს, ქმნის ალტერნატივებს და გეგმებს;
- deterministic software მართავს state-ს, permissions-ს, policy-ს, authorization-სა და execution gate-ებს;
- execution ქმნის verifiable evidence-ს;
- Critic / Verifier დამოუკიდებლად ამოწმებს შედეგს;
- real-world outcome ცალკე განიხილება execution success-ისა და verification success-ისგან;
- self-improvement გადის evaluation, regression, approval და promotion პროცესს.

ეს repository არის **public architecture / protocol showcase** და არა private runtime-ის open-source distribution.

## რატომ არ არის ეს prompt wrapper

ჩვეულებრივი prompt wrapper:

```text
User -> Prompt -> LLM -> Response
```

ამ protocol-ის სამიზნე არქიტექტურა:

```text
Objective
-> Decision Intelligence
-> Typed Contracts
-> Deterministic Control Plane
-> Policy / Authorization
-> Authorized Execution
-> Evidence
-> Independent Verification
-> Real-World Outcome
-> Governed Improvement
```

## მთავარი პრინციპი

```text
Models reason.
Software controls state and authority.
```

Model-ს შეუძლია plan-ის შეთავაზება, მაგრამ model-მა თვითონ არ უნდა შეძლოს გადაწყვიტოს, გაიარა თუ არა policy gate, აქვს თუ არა production permission, ან შეიძლება თუ არა destructive action-ის შესრულება.

## ძირითადი ფენები

1. **Prompt Brain / Decision Intelligence** - problem framing, method selection, alternatives, evidence requirements, planning.
2. **Deterministic Control Plane** - state, policies, permissions, approvals, budgets, authorization, audit.
3. **Execution Runtime** - მხოლოდ ავტორიზებული მოქმედებების შესრულება და evidence-ის შექმნა.
4. **Critic / Verifier** - independent verification, deterministic tests და AI-assisted review.
5. **Outcome & Improvement** - რეალური შედეგების დაკვირვება და controlled improvement pipeline.

## მნიშვნელოვანი განსხვავება

```text
Execution Success
!= Verification Success
!= Real-World Outcome
```

სისტემა deliberately არ აიგივებს „შესრულდა“, „სწორია“ და „რეალურ სამყაროში იმუშავა“ მდგომარეობებს.

## Private deployment

myGO ამ protocol-ის საფუძველზე სთავაზობს ორგანიზაციებს private implementation და deployment მომსახურებას, მათ შორის:

- Dedicated VPS / Dedicated Server;
- Private Cloud;
- On-Premises;
- Single-Tenant Enterprise;
- Self-Hosted;
- Hybrid Model Access;
- customer-specific security and approval policies.

## PHP-native private implementation

PHP-native ვარიანტი ნიშნავს deterministic control architecture-ის PHP-ში რეალიზაციას და არა AI model-ის PHP-ში გადაწერას.

შესაძლო private architecture:

```text
PHP Web UI
PHP API
PHP Control Plane
PHP Policy Enforcement
MariaDB / MySQL
Queue / Workers
Model Gateway
Tool Adapters
Audit / Evidence Storage
```

საჭიროების შემთხვევაში specialized Python / Node workers შეიძლება დაემატოს ისე, რომ provider-neutral contracts არ შეიცვალოს.

## Public repository boundary

Public repository-ში შეგნებულად არ ქვეყნდება:

- proprietary prompts;
- private evaluator datasets;
- security-sensitive policies;
- internal authorization logic;
- commercial connectors;
- deployment secrets;
- customer-specific integrations;
- proprietary improvement logic;
- private production source code.

## სტატუსი

**Public Status: Architecture Specification / Protocol Documentation**

README და docs აღწერს target architecture-სა და public contract-ს. ყველა აღწერილი შესაძლებლობა არ უნდა ჩაითვალოს ავტომატურად საჯაროდ ხელმისაწვდომ working implementation-ად.

## ლიცენზია

ეს არის **public documentation**, არა open-source software distribution.

Copyright © 2026 myGO LLC. All rights reserved.

---

**Reason with AI. Authorize with software. Verify with evidence. Improve under governance.**
