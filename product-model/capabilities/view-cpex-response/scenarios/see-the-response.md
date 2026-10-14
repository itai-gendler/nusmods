---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens CPEx signed in"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product loads the student's response from the university and shows the intended units and each course with its degree requirement, in order, against the limit of seven"
    kind: product
    actor: student
    entities:
      - { entity: cpex-submission, effect: reads, facts: [Intended units] }
      - { entity: cpex-course, effect: reads, facts: [Course, Rank, Degree requirement] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# See the response

## Trigger

The signed-in student opens CPEx.

## Outcome

The student sees their courses in order with what each counts towards, and their intended units.

## Edge cases

- A student who has not responded yet starts with no courses and 0 units.
