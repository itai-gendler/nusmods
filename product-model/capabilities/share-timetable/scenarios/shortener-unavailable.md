---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student chooses Shorten link"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The link shortener does not answer, or the student is offline"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product keeps the full link and says the link shortener is temporarily unavailable"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
---

# Link shortener unavailable

## Trigger

The student asks for a short link while the shortener cannot be reached or they are offline.

## Outcome

The student keeps the full link.
