---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student searches the CPEx course list and picks a course"
    kind: actor
    actor: student
    entities:
      - { entity: cpex-course, effect: reads, facts: [] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product adds it last in the order as an Essential Major and saves the response to the university"
    kind: product
    actor: student
    entities:
      - { entity: cpex-course, effect: creates, facts: [Course, Rank, Degree requirement] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Add a course

## Trigger

The student intends to take a course next semester.

## Outcome

The course is last in the student's order, as an Essential Major, and the response is saved.

## Edge cases

- Only courses in the CPEx course list for the round can be picked.
