---
kind: alternative
routes:
  web: Web
steps:
  - text: "The Student changes the prerequisite tree direction, beta testing, usage tracking or whether reviews load manually"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::settings" } }
  - text: "The Product keeps the choices"
    kind: product
    actor: student
    entities:
      - { entity: student, effect: changes, facts: [Prerequisite tree direction, Beta testing, Usage tracking, Load reviews manually] }
    contexts: { web: { place: "web::public::settings" } }
---

# Change other settings

## Trigger

The student wants to change how course pages or tracking behave.

## Outcome

The choices take effect.
