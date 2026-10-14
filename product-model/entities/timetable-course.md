---
references:
  - { kind: code, role: implementation, target: website/src/reducers/timetables.ts }
  - { kind: code, role: implementation, target: website/src/types/views.ts }
---

# Timetable course

A course added to a semester's timetable, with the classes the student chose for it.

## Information kept

- **Course** — which course it is
- **Lessons chosen** — one class of each lesson type, or in TA mode any number of lessons of each type
- **Color** — the colour it is drawn in, from the student's theme
- **TA mode** — whether the student teaches it rather than takes it, letting them choose several lessons of a type

## States

### Shown

Its lessons show on the timetable and count towards exam clashes.

### Hidden

Kept in the timetable but its lessons are not drawn, and it is left out of exam clashes and active units.
