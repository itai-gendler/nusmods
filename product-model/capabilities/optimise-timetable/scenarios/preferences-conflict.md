---
kind: validation
routes:
  web: Web
steps:
  - text: "The Student chooses free days, hours or pins that a pinned or only class cannot meet"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "A physical lesson must fall on a free day or outside the hours, or two pinned classes overlap"
    kind: condition
    actor: student
    entities:
      - { entity: course, effect: reads, facts: [Lessons] }
    contexts: { web: { place: "web::public::optimiser" } }
  - text: "The Product names the conflicting lessons and keeps Optimise unavailable"
    kind: product
    actor: student
    entities: []
    contexts: { web: { place: "web::public::optimiser" } }
---

# Preferences conflict

## Trigger

A pinned class falls on a free day or outside the chosen hours, or two pinned classes clash.

## Outcome

Optimise stays unavailable until the student resolves the conflict shown.

## Edge cases

- Optimise is also unavailable while the timetable has no courses.
