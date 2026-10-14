---
kind: edge
routes:
  api: Public API
steps:
  - text: "The Developer requests a code not in that year's data"
    kind: actor
    actor: developer
    entities: []
    contexts: { api: { place: public-api } }
  - text: "The Product answers that nothing was found"
    kind: product
    actor: developer
    entities: []
    contexts: { api: { place: public-api } }
---

# Course not published

## Trigger

The code is not in that year's data.

## Outcome

The developer gets nothing for the code.
