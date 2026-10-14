---
appliesTo:
  - { type: capability, id: add-cpex-course }
  - { type: entity, id: cpex-course, effect: creates }
references:
  - { kind: code, role: implementation, target: website/src/views/mpe/constants.ts }
  - { kind: code, role: implementation, target: website/src/views/mpe/form/ModuleForm.tsx }
---

# A CPEx response holds at most seven courses, each once

A student can name up to seven courses in the Course Planning Exercise, and the same course only once. The number of intended units does not change that limit.
