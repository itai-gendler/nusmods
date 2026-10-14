---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Download, then PDF (.pdf)"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product renders the semester's timetable as a PDF and downloads it"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen, Color] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Download a PDF

## Trigger

The student wants to print their timetable.

## Outcome

The student has a PDF of the timetable.
