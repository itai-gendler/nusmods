---
domain: timetable
availability:
  - { place: web::public }
references:
  - { kind: code, role: implementation, target: website/src/views/timetable/ExportMenu.tsx }
  - { kind: code, role: implementation, target: website/src/actions/export.ts#downloadAsIcal }
  - { kind: code, role: implementation, target: website/src/apis/export.ts }
  - { kind: code, role: implementation, target: export/src/handler.ts }
  - { kind: code, role: implementation, target: website/src/utils/ical.ts }
---

# Download a timetable

Download the semester's timetable as an image, a PDF, or an iCalendar file for Google Calendar or Outlook.
