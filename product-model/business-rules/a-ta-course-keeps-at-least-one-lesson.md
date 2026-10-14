---
appliesTo:
  - { type: capability, id: remove-ta-lesson }
  - { type: entity, id: timetable-course, effect: changes, facts: [Lessons chosen] }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/TimetableContent.tsx#TimetableContent }
---

# A course in TA mode keeps at least one lesson

Removing a lesson from a course in TA mode is refused when it is the course's last chosen lesson.
