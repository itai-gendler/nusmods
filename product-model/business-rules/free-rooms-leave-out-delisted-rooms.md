---
appliesTo:
  - { type: capability, id: find-free-rooms }
  - { type: entity, id: venue, facts: [Occupancy] }
references:
  - { kind: code, role: implementation, target: website/src/utils/venues.ts#filterAvailability }
  - { kind: code, role: implementation, target: website/src/data/excludedFreeRooms.ts }
---

# Free rooms leave out rooms delisted by their departments

A venue is free when none of the half hours chosen has a lesson there, and a venue with no lessons that day is free. Rooms whose departments asked to be delisted, such as meeting rooms with the odd lesson, never appear as free.

## Rationale

Students sent to a room that is not really for them end up being asked to leave.
