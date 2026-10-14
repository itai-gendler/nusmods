---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens the planner Settings and picks the year they matriculated in and the year they expect to graduate"
    kind: actor
    actor: student
    entities:
      - { entity: planner, effect: reads, facts: [] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product keeps the years, moving the other one along where needed so graduation is never before matriculation"
    kind: product
    actor: student
    entities:
      - { entity: planner, effect: changes, facts: [Matriculation year, Graduation year] }
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Student turns Taking iBLOCs and Ignore Prerequisite Checking on or off"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::planner" } }
  - text: "The Product keeps the choices, showing an iBLOCs list before matriculation when on"
    kind: product
    actor: student
    entities:
      - { entity: planner, effect: changes, facts: [iBLOCs, Ignore prerequisite checking] }
    contexts: { web: { place: "web::public::planner" } }
---

# Set the years

## Trigger

The student sets up their plan.

## Outcome

The plan spans the chosen years, with iBLOCs and prerequisite checking as chosen.

## Edge cases

- Matriculation can be chosen up to five years back and one year ahead; graduation up to six years ahead.
