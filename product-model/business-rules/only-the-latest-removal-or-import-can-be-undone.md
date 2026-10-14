---
appliesTo:
  - { type: capability, id: undo-timetable-change }
  - { type: capability, id: reset-timetable }
references:
  - { kind: code, role: implementation, target: website/src/reducers/index.ts }
  - { kind: code, role: implementation, target: website/src/reducers/undoHistory.ts#computeUndoStacks }
---

# Only the latest removal or import can be undone

NUSMods remembers one step back: undoing restores the timetables as they were before the latest course removal or timetable import. Resetting a timetable cannot be undone.
