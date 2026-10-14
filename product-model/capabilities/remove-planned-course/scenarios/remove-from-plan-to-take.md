---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student chooses to take the course off their Plan to Take list on its course page"
    kind: actor
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
  - text: "The Product removes the course from the Plan to Take list"
    kind: product
    actor: student
    entities:
      - { entity: planned-course, effect: removes }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::course-page" } }
---

# Remove from Plan to Take

## Trigger

The student is on the page of a course in their Plan to Take list.

## Outcome

The course leaves Plan to Take.
