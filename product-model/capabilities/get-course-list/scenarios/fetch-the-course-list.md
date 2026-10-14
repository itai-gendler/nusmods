---
kind: primary
routes:
  api: Public API
steps:
  - text: "The Developer requests the course list of an academic year"
    kind: actor
    actor: developer
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { api: { place: public-api } }
  - text: "The Product returns every course with its code, title and semesters offered"
    kind: product
    actor: developer
    entities:
      - { entity: course, effect: reads, facts: [Code, Title, Semesters offered] }
    contexts: { api: { place: public-api } }
---

# Fetch the course list

## Trigger

A developer needs the catalogue.

## Outcome

The developer has every course of the year.

## Edge cases

- A fuller list adds each course's description, faculty, department, units, requisites and each semester's exam.
