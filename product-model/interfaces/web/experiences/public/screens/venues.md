---
entities:
  - { entity: venue, shows: [Name, Room name] }
entryPoints:
  - web: /venues
references:
  - { kind: code, role: implementation, target: website/src/views/venues/VenuesContainer.tsx }
  - { kind: code, role: implementation, target: website/src/views/venues/VenueList.tsx }
---

# Venues

The list of venues, narrowed by a search or to the rooms free at a chosen time.
