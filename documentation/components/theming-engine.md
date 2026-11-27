# C-01 — Theming Engine

**Status:** Draft · **Build** around an existing palette generator (P0)

## Responsibilities
1. Hold state: `colorSource`, current wallpaper, custom colors (via Settings Store).
2. Produce the active palette (US-02 / US-03 rules), cached by image hash.
3. Render templates for all consumers and signal reload (IF-01).
4. Accept commands (IF-02).

## Consumers (each needs a template + reload method)
| Consumer | Reload method | Status |
|----------|--------------|--------|
| Shell UI (all C-1x) | change signal | TBD-008 |
| Hyprland (borders, shadows) | `hyprctl` keyword/reload | Draft |
| kitty | remote control / SIGUSR1 | Draft |
| GTK 3/4 | CSS + settings | Draft |
| Qt (qt5ct/qt6ct or Kvantum) | — | TBD-046 |
| Launcher | per ADR | Draft |

## Requirements
Functional requirements: REQ-THM-001 … 006 (US-02), REQ-CCM-001 … 007 (US-03), SYS-001.

| ID | Requirement | Verif. |
|----|-------------|--------|
| REQ-THE-001 | Adding a new consumer shall only require adding a template and a reload hook (no engine code change). | I |
| REQ-THE-002 | A failing consumer reload shall be logged and shall not block other consumers. | T |
