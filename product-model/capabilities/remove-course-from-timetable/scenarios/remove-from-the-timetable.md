---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Remove on a timetable course"
    kind: actor
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product removes the timetable course and shows a \"removed\" notice in its place with Undo and Dismiss"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: removes, from: Shown }
    contexts: { web: { place: "web::public::timetable" } }
---

# Remove from the timetable

## Trigger

The student drops a course.

## Outcome

The course and its lessons leave the timetable; a notice in its place offers Undo.

## Edge cases

- A hidden course is removed the same way.
