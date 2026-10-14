---
domain: cpex
relations:
  - { entity: cpex-course, verb: lists, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: website/src/types/mpe.ts }
  - { kind: code, role: implementation, target: website/src/serverless/mpe.ts }
---

# CPEx submission

A student's response to the Course Planning Exercise for the coming semester, kept by the university.

## Information kept

- **Intended units** — how many units the student intends to take; it starts at 0
