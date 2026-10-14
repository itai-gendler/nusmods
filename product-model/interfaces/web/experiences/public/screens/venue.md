---
entities:
  - { entity: venue, shows: [Name, Room name, Floor, Location, Lessons] }
entryPoints:
  - web: /venues/LT27
references:
  - { kind: code, role: implementation, target: website/src/views/venues/VenueDetails.tsx }
  - { kind: code, role: implementation, target: website/src/views/venues/VenueLocation/VenueLocation.tsx }
---

# Venue

One venue: where it is and its weekly lessons.
