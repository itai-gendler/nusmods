---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Undo where the removed course was listed"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product puts the timetable back as it was before the removal"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Undo removing a course

## Trigger

The student removed a course by mistake.

## Outcome

The course is back with the classes, colour and visibility it had.

## Edge cases

- Dismiss clears the notice and the course stays removed.
- A course that was hidden comes back hidden.
