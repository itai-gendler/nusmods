---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens CPEx signed in"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The sign-in is no longer accepted"
    kind: condition
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
  - text: "The Product says the session has expired and asks the student to sign in again"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::signed-in::cpex-response" } }
---

# Session expired

## Trigger

The student's sign-in has expired.

## Outcome

The student is told the session expired and is signed out to sign in again.
