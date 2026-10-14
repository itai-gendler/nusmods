---
entities:
  - { entity: cpex-submission, shows: [Intended units], collects: [Intended units] }
  - { entity: cpex-course, shows: [Course, Rank, Degree requirement], collects: [Degree requirement] }
  - { entity: course, shows: [Code, Title, Units] }
references:
  - { kind: code, role: implementation, target: website/src/views/mpe/form/ModuleForm.tsx }
  - { kind: code, role: implementation, target: website/src/views/mpe/form/MpeFormContainer.tsx }
---

# CPEx response

The signed-in student's Course Planning Exercise response, saved as they change it.
