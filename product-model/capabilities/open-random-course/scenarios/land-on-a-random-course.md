---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student chooses Random Course in the course finder"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-finder" } }
  - text: "The Product picks a course at random among those matching the search and filters and opens its course page"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Code] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Land on a random course

## Trigger

The student wants to discover a course.

## Outcome

The student is on the page of a course matching their filters.
