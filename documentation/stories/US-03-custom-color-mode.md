# US-03 — Custom Color Mode

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P4 |
| Priority | Should |
| Components | C-01 Theming Engine, C-14 Settings App |
| Depends on | US-02, SYS-004 |
| Keybinds | KB-02 (SUPER+SHIFT+B) |

## Stakeholder need
As the User, I want to toggle a custom color mode in which the colors are my chosen
primary and secondary color and do not follow the wallpaper. I pick these colors in
the Settings App with a visual color picker.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-CCM-001 | KB-02 shall toggle the color source between `wallpaper` and `custom`. | T | Two presses return to the original source and palette. |
| REQ-CCM-002 | In `custom` mode, the palette shall be derived from the custom primary and secondary color; wallpaper changes shall not alter the palette. | T | Change wallpaper in custom mode → palette unchanged. |
| REQ-CCM-003 | Switching back to `wallpaper` shall restore the palette of the current wallpaper (from cache, REQ-THM-003). | T | — |
| REQ-CCM-004 | The Settings App shall provide a visual color picker (hue/saturation area + hex input, TBR-033) for primary and secondary. | D | — |
| REQ-CCM-005 | Color source and custom colors shall persist across reboot. | T | — |
| REQ-CCM-006 | Toggling shall give visual feedback via a brief Island activity showing the new mode (TBR-034). | D | — |
| REQ-CCM-007 | Derivation of the remaining roles (surface, outline …) from two custom colors: TBD-023. | — | — |
