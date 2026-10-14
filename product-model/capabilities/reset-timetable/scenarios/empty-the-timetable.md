---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Reset on the Timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product asks whether to permanently remove every course in the timetable for this semester"
    kind: product
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [Semester] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student confirms"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product removes every course from the semester's timetable"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: removes, from: Shown }
      - { entity: timetable, effect: reads, facts: [] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Empty the timetable

## Trigger

The student wants to start the semester over.

## Outcome

The semester's timetable has no courses; the reset cannot be undone.

## Edge cases

- Hidden and TA mode courses go too.
- Closing the question leaves the timetable as it was.
