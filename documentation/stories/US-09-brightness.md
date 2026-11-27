# US-09 — Brightness Control

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P1 (OSD fallback), P2 (Island) |
| Priority | Must |
| Components | C-11 Dynamic Island, C-10 Top Bar (Control Centre) |
| Depends on | IF-09, SYS-005 |
| Keybinds | KB-08, KB-09 |

## Stakeholder need
As the User, I want to control brightness with the brightness function keys or in the
Control Centre. With function keys, the Island pops up showing a slider and a
percentage. In the Control Centre I can drag without a grid.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-BRT-001 | KB-08 shall change brightness by a fixed step (TBD-015, proposal 5 %), snapped to the step grid. | T | 47 % + up → 50 %. |
| REQ-BRT-002 | KB-09 (with SHIFT) shall use a fine step (TBD-015, proposal 2 %). | T | — |
| REQ-BRT-003 | Brightness shall be clamped to [min, 100 %], min = TBR-041 (proposal 1 %, never fully off). | T | — |
| REQ-BRT-004 | Each key press shall show the brightness Island Activity: slider + percentage to its right. | D | — |
| REQ-BRT-005 | The Island slider shall be draggable/adjustable with LEFT/RIGHT while open (TBR-042). | D | — |
| REQ-BRT-006 | The Control Centre brightness slider shall be continuous (no snapping). | T | Drag to 37 % → 37 %. |
| REQ-BRT-007 | Island and Control Centre shall always show the same current value, including changes made by other tools. | T | — |
| REQ-BRT-008 | Until the Island exists (Phase P1), a minimal OSD shall satisfy REQ-BRT-004. | D | — |
| REQ-BRT-009 | Mapping of percentage to hardware value: linear or perceptual (OLED) — TBD-032. | — | — |
