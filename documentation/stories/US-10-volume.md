# US-10 — Volume Control

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P1 (OSD fallback), P2 (Island) |
| Priority | Must |
| Components | C-11 Dynamic Island, C-10 Top Bar (Control Centre) |
| Depends on | IF-08, SYS-005 |
| Keybinds | KB-10, KB-11, KB-12 |

## Stakeholder need
As the User, I want to control the volume with the function keys or in the Control
Centre. With function keys, the Island pops up showing a slider and percentage,
snapping to 5 % steps, or 2 % steps while holding SHIFT. In the Control Centre
dragging is continuous.

*Correction vs. draft v0.1: the draft said "show the current brightness" — volume is meant.*

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-VOL-001 | KB-10 shall change the default sink volume by 5 %, snapped to the 5 % grid. | T | 47 % + up → 50 %; 50 % + up → 55 %. |
| REQ-VOL-002 | KB-11 (with SHIFT) shall change volume by 2 %, snapped to the 2 % grid. | T | 47 % + up → 48 %. |
| REQ-VOL-003 | Volume shall be clamped to [0 %, 100 %]; over-amplification: TBD-033. | T | — |
| REQ-VOL-004 | Each key press shall show the volume Island Activity: slider + percentage to its right; a mute state shall be visibly distinct. | D | — |
| REQ-VOL-005 | KB-12 shall toggle mute; volume keys while muted shall unmute (TBR-013). | T | — |
| REQ-VOL-006 | The Control Centre volume slider shall be continuous (no snapping). | T | — |
| REQ-VOL-007 | Island and Control Centre shall always show the same value, including external changes (e.g. app or headset buttons). | T | — |
| REQ-VOL-008 | Volume changes shall apply to the current default output device; device switching is out of scope here (TBD-034). | T | — |
| REQ-VOL-009 | Until the Island exists (Phase P1), a minimal OSD shall satisfy REQ-VOL-004. | D | — |
