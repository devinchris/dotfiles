# US-05 — Keybind Menu

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P4 (read-only view may ship in P1, TBR-036) |
| Priority | Should |
| Components | C-15 Keybind Menu, C-02 Keybind Registry |
| Depends on | SYS-003, IF-03, IF-04 |
| Keybinds | KB-04 (CTRL+SUPER+K) |

## Stakeholder need
As the User, I want a searchable menu showing all keyboard shortcuts, where I can also
change shortcuts. Keys are drawn as key caps, not plain text.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-KBM-001 | KB-04 shall toggle the Keybind Menu. | D | — |
| REQ-KBM-002 | The menu shall list every binding of the Keybind Registry with description and category. | T | Count equals registry entries. |
| REQ-KBM-003 | Typing shall filter by description, action name and key names. | T | "dock" shows KB-05. |
| REQ-KBM-004 | Keys shall be rendered as key caps per 05 §5. | D | — |
| REQ-KBM-005 | The User shall be able to select a binding and record a new key combination. | D | — |
| REQ-KBM-006 | A recorded combination already in use shall be rejected with a message naming the conflicting binding. | T | Conflict → no write, message shown. |
| REQ-KBM-007 | An accepted change shall be written to the registry, the Hyprland config regenerated and reloaded; the new shortcut shall work immediately and the old one shall stop working. | T | — |
| REQ-KBM-008 | The User shall be able to reset a binding to its default. | T | — |
| REQ-KBM-009 | Bindings marked `locked` in the registry (e.g. emergency/exit binds) shall not be editable (TBD-024). | T | — |
