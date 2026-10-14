---
kind: primary
result: achieved
routes:
  web: Web
steps:
  - text: "The Student chooses to sign in on CPEx and signs in at NUS"
    kind: actor
    actor: student
    capability: sign-in-to-cpex
    entities: []
    contexts: { web: { place: "web::public::cpex" } }
  - text: "The Product takes the student back to CPEx signed in, ready to give their response"
    kind: product
    actor: student
    capability: sign-in-to-cpex
    entities: []
    contexts: { web: { place: "web::public::cpex" } }
  - text: "The Student picks a course to add"
    kind: actor
    actor: student
    capability: add-cpex-course
    entities:
      - { entity: course, effect: reads, facts: [] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product adds it to the response and saves"
    kind: product
    actor: student
    capability: add-cpex-course
    entities:
      - { entity: cpex-course, effect: creates, facts: [Course, Rank, Degree requirement] }
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Sign in and add a course

## Trigger

The Course Planning Exercise is open.

## Outcome

The student's response holds the course they added.
