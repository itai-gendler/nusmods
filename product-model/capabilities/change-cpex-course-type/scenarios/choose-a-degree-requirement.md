---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student picks Essential Major, Essential Second Major, Elective or Unrestricted Elective for a CPEx course"
    kind: actor
    actor: student
    entities:
      - { entity: cpex-course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product sets the course's degree requirement and saves the response"
    kind: product
    actor: student
    entities:
      - { entity: cpex-course, effect: changes, facts: [Degree requirement] }
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Choose a degree requirement

## Trigger

The course counts towards something other than the student's major.

## Outcome

The course carries the chosen degree requirement and the response is saved.
