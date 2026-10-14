---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The Student chooses Optimise"
    kind: actor
    actor: student
    capability: optimise-timetable
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Product offers Open Optimised Timetable"
    kind: product
    actor: student
    capability: optimise-timetable
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Student opens the optimised timetable and chooses Import"
    kind: actor
    actor: student
    capability: import-shared-timetable
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product replaces the semester's timetable courses with the optimised ones"
    kind: product
    actor: student
    capability: import-shared-timetable
    entities:
      - { entity: timetable-course, as: saved, effect: removes, from: Shown }
      - { entity: timetable-course, as: optimised, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Import the optimised timetable

## Trigger

The student wants a timetable that fits their preferences.

## Outcome

The optimised timetable replaces the student's saved one.
