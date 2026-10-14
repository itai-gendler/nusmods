---
domain: venues
references:
  - { kind: code, role: implementation, target: website/src/types/venues.ts }
  - { kind: code, role: implementation, target: scrapers/nus-v2/src/tasks/CollateVenues.ts }
  - { kind: code, role: implementation, target: website/src/data/venues.json }
---

# Venue

A room where lessons are held, such as a lecture theatre or seminar room.

## Information kept

- **Name** — the venue code the timetable uses, such as LT27
- **Room name** — the room's name, where known
- **Floor** — the floor the room is on, where known
- **Location** — where the room is on the campus map, where known
- **Occupancy** — for each day of the week, which half-hour slots have lessons
- **Lessons** — the lessons held there each week, with their course, lesson type, class, time and weeks
