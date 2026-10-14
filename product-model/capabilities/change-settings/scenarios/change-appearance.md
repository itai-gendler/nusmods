---
kind: primary
routes:
  web: Web
steps:
  - text: "The Student opens Settings and picks Night Mode on, off or following the device, and a theme"
    kind: actor
    actor: student
    entities: []
    contexts: { web: { place: "web::public::settings" } }
  - text: "The Product applies the colour scheme and theme everywhere"
    kind: product
    actor: student
    entities:
      - { entity: student, effect: changes, facts: [Color scheme, Theme] }
    contexts: { web: { place: "web::public::settings" } }
---

# Change appearance

## Trigger

The student wants NUSMods to look different.

## Outcome

NUSMods uses the chosen Night Mode and theme straight away.

## Edge cases

- Night Mode is also switched anywhere with the X key, and themes cycled with keyboard shortcuts.
