---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student opens a timetable share link"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows the shared timetable read-only"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Lessons] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Student chooses Back to saved timetable"
    kind: actor
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product shows the student's saved timetable for that semester"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Keep the saved timetable

## Trigger

The student only wanted to look at a shared timetable.

## Outcome

The student is back on their own saved timetable, unchanged.
