---
kind: alternative
routes:
  web: Web
steps:
  - text: "The refresh schedule comes round"
    kind: condition
    unattended: true
    entities: []
  - text: "A course in the catalogue has no semester this academic year"
    kind: condition
    entities:
      - { entity: course, effect: reads, facts: [Semesters offered] }
  - text: "The Product keeps the course as not offered"
    kind: product
    entities:
      - { entity: course, effect: changes, from: Offered, to: Not offered, facts: [Semesters offered] }
    contexts: { web: { place: "web::public::course-page" } }
---

# A course stops being offered

## Trigger

The refresh finds a course listed in the catalogue with no semester this year.

## Outcome

The course page says it is not offered this academic year.
