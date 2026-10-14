---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student removes a CPEx course"
    kind: actor
    actor: student
    entities:
      - { entity: cpex-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product removes it, moves the courses after it up and saves the response"
    kind: product
    actor: student
    entities:
      - { entity: cpex-course, effect: removes }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Remove a course

## Trigger

The student no longer intends to take a course.

## Outcome

The course is gone, the rest move up, and the response is saved.
