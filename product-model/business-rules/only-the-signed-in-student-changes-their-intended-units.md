---
appliesTo:
  - { type: entity, id: cpex-submission, effect: changes }
permits:
  - { related: [{ verb: owns, entity: student }], when: [{ entity: site-configuration, fact: CPEx open, is: "Yes" }] }
references:
  - { kind: code, role: implementation, target: website/api/nus/mpe/submissions.ts }
---

# Only the signed-in student changes their intended units, while CPEx is open

The intended units of a response change only through its own student's sign-in, while the exercise is open.
