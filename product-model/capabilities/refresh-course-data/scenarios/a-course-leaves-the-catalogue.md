---
kind: alternative
routes:
  web: Web
steps:
  - text: "The refresh schedule comes round"
    kind: condition
    unattended: true
    entities: []
  - text: "A course published before is no longer active in the university's data"
    kind: condition
    entities:
      - { entity: course, effect: reads, facts: [Code] }
  - text: "The Product removes the course from this year's data"
    kind: product
    entities:
      - { entity: course, effect: removes, from: Offered }
    contexts: { web: { place: "web::public::course-page" } }
---

# A course leaves the catalogue

## Trigger

The refresh no longer finds a course the university used to list.

## Outcome

The course is gone from this year's catalogue; its page falls back to the archives.

## Edge cases

- A course not offered this year leaves the same way.
