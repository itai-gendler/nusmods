---
appliesTo:
  - { type: entity, id: cpex-course, facts: [Rank] }
references:
  - { kind: code, role: implementation, target: website/src/serverless/mpe.ts#createSubmission }
---

# CPEx courses are ranked in the order listed

The university receives the courses ranked by their order in the response, first as rank 1.
