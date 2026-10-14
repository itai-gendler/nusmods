---
entities:
  - { entity: student, shows: [Color scheme, Theme, Prerequisite tree direction, CourseReg reminders, Course type, Dismissed reminders, Beta testing, Usage tracking, Load reviews manually], collects: [Color scheme, Theme, Prerequisite tree direction, CourseReg reminders, Course type, Dismissed reminders, Beta testing, Usage tracking, Load reviews manually] }
entryPoints:
  - web: /settings
references:
  - { kind: code, role: implementation, target: website/src/views/settings/SettingsContainer.tsx }
---

# Settings

The student's settings: Night Mode, theme, prerequisite tree direction, CourseReg reminders, beta features and privacy.
