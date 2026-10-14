---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses Shorten link"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
  - text: "The Product asks the NUSMods link shortener for a short link and shows it, with its QR code, in place of the full one"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::timetable" } }
---

# Shorten the link

## Trigger

The student wants a shorter link.

## Outcome

The student shares a short link that leads to the same timetable.

## Edge cases

- Show original link switches back to the full link.
