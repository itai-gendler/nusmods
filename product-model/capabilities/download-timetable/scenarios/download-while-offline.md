---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student chooses Download while offline"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The student is offline"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product offers only the iCalendar file, since images and PDFs are made online"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
---

# Download while offline

## Trigger

The student is offline.

## Outcome

Only the iCalendar file can be downloaded.
