---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens CPEx"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::cpex" } }
  - text: "The Product explains the exercise, its round and dates and that it is for planning only, and offers sign-in"
    kind: product
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [CPEx open, CPEx round] }
    contexts: { web: { place: "web::public::cpex" } }
  - text: "The Student chooses to sign in and signs in at NUS"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::cpex" } }
  - text: "The Product takes the student back to CPEx signed in, ready to give their response"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::cpex" } }
---

# Sign in with NUS

## Trigger

The student wants to give their CPEx response.

## Outcome

The student is signed in and lands on their CPEx response.

## Edge cases

- Signing in with the NUSID in the form nusstu\e0123456 is suggested when sign-in fails.
