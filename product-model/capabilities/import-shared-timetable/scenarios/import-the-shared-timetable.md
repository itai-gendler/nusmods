---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens a timetable share link"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product loads the courses in the link and shows the shared timetable read-only, saying it was shared and that importing will replace the saved timetable"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Lessons] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student chooses Import"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product replaces the semester's timetable courses with the shared ones, keeping which are hidden or in TA mode, and offers Undo"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, as: saved, effect: removes, from: Shown }
      - { entity: timetable-course, as: shared, effect: creates, to: Shown, facts: [Course, Lessons chosen, Color, TA mode] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Import the shared timetable

## Trigger

The student opens a timetable share link.

## Outcome

The shared timetable replaces the student's saved timetable for that semester, with an Undo on the notice.

## Edge cases

- Shared courses the link marks hidden arrive hidden.
- Courses in the link that the catalogue no longer has are left out.
