---
kind: validation
routes:
  web: Web
steps:
  - text: "The Student imports a file"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::planner" } }
  - text: "The file is not a valid planner file"
    kind: condition
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product leaves the plan as it is and says the uploaded file does not seem valid"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::planner" } }
---

# File not valid

## Trigger

The file is not a planner file.

## Outcome

The plan is unchanged and the student is told the file does not seem valid.

## Edge cases

- A file that cannot be read is reported as an upload problem to try again.
