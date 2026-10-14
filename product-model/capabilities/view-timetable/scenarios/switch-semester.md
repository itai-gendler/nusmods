---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student picks another semester in the semester switcher"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product opens that semester's timetable and remembers it as the semester to open next time"
    kind: product
    actor: student
    entities:
      - { entity: timetable, effect: reads, facts: [Semester] }
    contexts: { web: { place: "web::public::timetable" } }
---

# Switch to another semester

## Trigger

The student wants to plan another semester.

## Outcome

The Timetable shows the chosen semester's timetable.
