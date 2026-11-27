# 06 — Keybind Registry (specification view)

This table is the **specification**. The implementation lives in the keybind data
file (SYS-003); both shall be kept consistent (checked by test VT-KB-01).

| KB-ID | Keys | Action (IF-06) | Story | Status |
|-------|------|---------------|-------|--------|
| KB-01 | SUPER + SHIFT + W | `island.wallpaper` | US-01 | Approved |
| KB-02 | SUPER + SHIFT + B | `theming.toggleColorSource` | US-03 | Approved |
| KB-03 | SUPER + SPACE *(alt: CTRL + SUPER + SPACE)* | `launcher.toggle` | US-04 | TBD-014 |
| KB-04 | CTRL + SUPER + K | `keybindmenu.toggle` | US-05 | Approved |
| KB-05 | CTRL + SUPER + D | `dock.toggle` | US-06 | Approved |
| KB-06 | SUPER + RETURN | open kitty | US-07 | Approved |
| KB-07 | SUPER + SHIFT + P | `quickmenu.power` | US-08 | Approved |
| KB-08 | XF86MonBrightnessUp / Down | `brightness.step(±, default)` | US-09 | Approved |
| KB-09 | SHIFT + XF86MonBrightnessUp / Down | `brightness.step(±, fine)` | US-09 | TBD-015 |
| KB-10 | XF86AudioRaiseVolume / LowerVolume | `volume.step(±, 5 %)` | US-10 | Approved |
| KB-11 | SHIFT + XF86AudioRaiseVolume / LowerVolume | `volume.step(±, 2 %)` | US-10 | Approved |
| KB-12 | XF86AudioMute | `volume.mute` | US-10 | TBR-013 |
| KB-13 | XF86AudioPlay/Next/Prev | media control | US-12 | TBD-016 |

## Rules
- **No duplicates:** each key combination maps to at most one action (VT-KB-02).
- **Conflicts with defaults:** before approval, each combination shall be checked
  against Hyprland defaults, the launcher's own bindings and common app shortcuts
  (e.g. SUPER+SPACE vs. keyboard layout switching) → TBD-014.
- Window-management binds (focus, move, workspaces) are to be added here in the
  same format → TBD-017.
