# US-11 — Pointer Acceleration & Speed

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P1 (config), P4 (Settings App UI) |
| Priority | Must |
| Components | Hyprland input config, C-14 Settings App |
| Depends on | SYS-004 |
| Keybinds | — |

## Stakeholder need
As the User, I want touchpad acceleration that feels like a MacBook trackpad, applied
only to the built-in touchpad, not an external mouse. If the default doesn't feel
right, smoothness shall be adjustable in the Settings App. Pointer speed shall be
configurable separately for touchpad and external mouse.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-INP-001 | The built-in touchpad shall use a custom acceleration profile approximating macOS trackpad behavior (curve definition: TBD-035). | D | User acceptance after trial (subjective; owner sign-off). |
| REQ-INP-002 | External mice shall use a separate profile (default: flat, TBR-043), unaffected by touchpad settings. | T | Change touchpad accel → mouse config unchanged. |
| REQ-INP-003 | Device matching shall be by device identity (name from `hyprctl devices`), not by device type guessing. | I | — |
| REQ-INP-004 | The Settings App shall expose: touchpad speed, touchpad acceleration/smoothness, mouse speed, mouse acceleration on/off — applied live. | D | Slider change takes effect without relogin. |
| REQ-INP-005 | Touchpad gestures and natural scrolling: TBD-036 (likely: natural scrolling on touchpad only, macOS-like). | — | — |

## Implementation notes
Hyprland supports per-device input sections and custom acceleration curves; the
curve points are the tuning parameter exposed as "smoothness".
