---
domain: planner
references:
  - { kind: code, role: implementation, target: website/src/types/planner.ts }
  - { kind: code, role: implementation, target: website/src/selectors/planner.ts }
---

# Planned course

A course, or a placeholder such as "Any GE module", placed in the planner.

## Information kept

- **Course** — the course code, once there is one
- **Placeholder** — the kind of course it stands for, when the student has not chosen one yet
- **Year** — the academic year it is planned for
- **Semester** — the semester it is planned for, or the Exemptions, Plan to Take or iBLOCs list
- **Position** — its place in the order of that semester
- **Warnings** — the problems the planner finds with it: unmet prerequisites, a semester it is not offered in, an exam clash, a duplicate in the semester, or no information about the code
