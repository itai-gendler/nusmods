---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens a course archive for a year the course did not exist"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-archive" } }
  - text: "The Product says the course could not be found"
    kind: product
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-archive" } }
---

# Archive not found

## Trigger

The course did not exist that year.

## Outcome

The student is told the course could not be found for that year.
