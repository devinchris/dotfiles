# US-06 — Mac-like App Dock

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P3 |
| Priority | Must |
| Components | C-12 App Dock |
| Depends on | IF-05, IF-01, SYS-004 |
| Keybinds | KB-05 (CTRL+SUPER+D) |

## Stakeholder need
As the User, I want a dock at the bottom with pinned and open apps (dot under open
apps), a Downloads folder shortcut, a right-click menu, click-to-focus, a toggle with
morph animation that is remembered, dynamic colors, and drag-to-resize like macOS.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-DCK-001 | The dock shall show pinned apps (in User-defined order) followed by running unpinned apps. | T | — |
| REQ-DCK-002 | Apps with ≥ 1 open window shall show a dot indicator below the icon. | T | Open/close app → dot appears/disappears. |
| REQ-DCK-003 | The dock shall contain a Downloads folder item, separated from apps, that opens the folder in the file manager (TBD-025: file manager; stack preview like macOS?). | D | — |
| REQ-DCK-004 | Left-click on a running app shall focus its most recent window (switching workspace if needed); on a non-running pinned app it shall launch it. | T | — |
| REQ-DCK-005 | Behaviour for apps with several windows on click: TBD-026 (cycle windows / show picker). | — | — |
| REQ-DCK-006 | Right-click shall open a context menu with at least: Open new window, Pin/Unpin, Close (all windows of app). | D | — |
| REQ-DCK-007 | Pinned apps shall be reorderable by drag & drop (TBR-037). | D | — |
| REQ-DCK-008 | KB-05 shall toggle dock visibility with a morph in/out animation (`motion.slow`). | D | — |
| REQ-DCK-009 | Visibility shall persist across reboot. | T | — |
| REQ-DCK-010 | The dock shall use palette colors and update live on palette change. | D | — |
| REQ-DCK-011 | Dragging the dock's resize handle/separator shall scale icon size continuously between min and max (TBR-038: 32–96 px); size shall persist. | D, T | — |
| REQ-DCK-012 | Whether windows may overlap the dock or the dock reserves space (exclusive zone), and whether it auto-hides: TBD-027. | — | — |
| REQ-DCK-013 | Hovering an icon shall show the app name as a tooltip (TBR-039). | D | — |
