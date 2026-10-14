---
appliesTo:
  - { type: entity, id: cpex-course, effect: changes }
permits:
  - { related: [{ verb: lists, entity: cpex-submission }, { verb: owns, entity: student }], when: [{ entity: site-configuration, fact: CPEx open, is: "Yes" }] }
references:
  - { kind: code, role: implementation, target: website/api/nus/mpe/submissions.ts }
---

# Only the signed-in student changes their CPEx courses, while CPEx is open

Reordering a response or changing what a course counts towards is open only to the student who signed in, while the exercise is open.
