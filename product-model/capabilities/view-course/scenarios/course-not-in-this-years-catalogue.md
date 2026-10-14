---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens a course page for a code not in this year's catalogue"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product looks for the course in the archives of past academic years"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code, Academic year] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product links to each academic year's archive of the course, or says the course was not found, usually because of a typo or because it is not offered this year"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Course not in this year's catalogue

## Trigger

The student opens a course code this year's catalogue does not have.

## Outcome

The student is offered the archives of the years the course was offered, or told the course was not found.
