---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Download, then Image (.png)"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product renders the semester's timetable with the student's colours, theme and Night Mode as an image and downloads it"
    kind: product
    actor: student
    entities:
      - { entity: timetable-course, effect: reads, facts: [Course, Lessons chosen, Color] }
      - { entity: student, effect: reads, facts: [Theme, Color scheme] }
      - { entity: timetable, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Download an image

## Trigger

The student wants a picture of their timetable.

## Outcome

The student has a PNG of the timetable as it looks on their screen, in their theme and Night Mode.
