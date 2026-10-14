---
domain: venues
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/venues/AvailabilitySearch.tsx }
  - { kind: code, role: implementation, target: website/src/utils/venues.ts#filterAvailability }
  - { kind: code, role: implementation, target: website/src/data/excludedFreeRooms.ts }
---

# Find free rooms

List the venues with no lessons for a chosen stretch of time on a chosen day.
