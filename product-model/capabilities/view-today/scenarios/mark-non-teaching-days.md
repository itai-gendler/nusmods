---
kind: edge
routes:
  web: Web
steps:
  - text: "The Student opens Today"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::today" } }
  - text: "A coming day is a public holiday, outside instructional weeks, or a weekend with no lessons"
    kind: condition
    actor: student
    entities:
      - { entity: site-configuration, effect: reads, facts: [Holidays] }
    contexts: { web: { place: "web::public::today" } }
  - text: "The Product groups consecutive such days as a holiday, recess, reading or examination period or a weekend"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::today" } }
---

# Days without teaching

## Trigger

Some of the coming days are holidays, recess, reading or exam weeks, or empty weekends.

## Outcome

Those days are grouped under what they are instead of listing lessons.
