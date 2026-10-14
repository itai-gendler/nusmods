---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Undo on the \"Timetable imported\" notice"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product removes the imported courses and puts back the timetable courses the import replaced"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, as: imported, effect: removes, from: Shown }
      - { entity: timetable-course, as: saved, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Undo an import

## Trigger

The student imported a shared timetable and wants their own back.

## Outcome

The semester's timetable is what it was before the import.
