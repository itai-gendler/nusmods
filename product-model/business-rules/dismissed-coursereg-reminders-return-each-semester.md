---
appliesTo:
  - { type: entity, id: student, facts: [Dismissed reminders] }
references:
  - { kind: code, role: implementation, target: website/src/reducers/settings.ts }
---

# Dismissed CourseReg reminders return each semester

A dismissed CourseReg reminder stays dismissed for the rest of the semester; when NUSMods moves to a new semester, every reminder shows again.
