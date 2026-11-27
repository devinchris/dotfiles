# C-14 — Settings App

**Status:** Draft · **Build** (P4)

## Purpose
One place for every setting of this system plus basic device settings.

## Pages (initial)
| Page | Settings | Source |
|------|----------|--------|
| Appearance | Color source, custom primary/secondary (color picker), wallpaper directory | US-02, US-03 |
| Dock | Visibility, size, pinned apps order | US-06 |
| Input | Touchpad speed/acceleration, mouse speed/acceleration | US-11 |
| Keyboard | Opens Keybind Menu or embeds it | US-05 |
| Power | Default mode, per-mode timeouts | US-08 |
| Display / Sound / Network / Bluetooth | "Basic device settings" — scope TBD-043 | — |

## Requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-SET-001 | The Settings App shall read and write only through the Settings Store (IF-07). | I | — |
| REQ-SET-002 | Changes shall apply live without restart; there is no "Apply" button (TBR-064). | D | — |
| REQ-SET-003 | Each setting shall offer reset to default. | T | — |
| REQ-SET-004 | Pages shall be searchable (TBR-065). | D | — |
| REQ-SET-005 | Window type: regular floating window vs. layer-shell overlay — decide in ADR (TBD-044). | — | — |
| REQ-SET-006 | Invocation: from Control Centre, launcher entry, and keybind TBD-045. | D | — |
