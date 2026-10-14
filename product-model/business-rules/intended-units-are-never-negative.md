---
appliesTo:
  - { type: capability, id: change-intended-units }
  - { type: entity, id: cpex-submission, facts: [Intended units] }
references:
  - { kind: code, role: implementation, target: website/src/apis/mpe.ts }
  - { kind: code, role: implementation, target: website/src/serverless/mpe.ts#createSubmission }
---

# Intended units are never negative

A CPEx response's intended units are a whole number of zero or more.
