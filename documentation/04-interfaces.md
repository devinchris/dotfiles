# 04 — Interface Control Document (ICD)

**Status:** Draft. Concrete formats/protocols are fixed by the planning agent (ADR)
and then entered here. Every interface has exactly one owner (provider).

| ID | Provider → Consumer | Content | Mechanism | Status |
|----|--------------------|---------|-----------|--------|
| IF-01 | Theming Engine → all UI components, kitty, Hyprland, GTK/Qt | Active palette (roles per 05 §3) | Generated files + change signal | TBD-008 |
| IF-02 | UI (Island picker, Settings) → Theming Engine | `setWallpaper(path)`, `setColorSource(wallpaper\|custom)`, `setCustomColors(primary, secondary)` | IPC command | TBD-008 |
| IF-03 | Keybind Registry → Hyprland | Generated bind config | Generated file + `hyprctl reload` | TBD-009 |
| IF-04 | Keybind Registry ↔ Keybind Menu | List of bindings (id, keys, action, description, category); write-back of changed keys | File read/write + validation | TBD-009 |
| IF-05 | Hyprland → Shell | Windows, workspaces, focus, open/close events | Hyprland IPC socket | Fixed (Hyprland) |
| IF-06 | Keybind → Shell | Shell actions triggered by shortcuts (e.g. `island.open wallpaper`, `quickmenu.open power`, `dock.toggle`) | Shell IPC command | TBD-010 |
| IF-07 | Settings Store ↔ all components | Read settings, write settings, change notification | File + watch / IPC | TBD-011 |
| IF-08 | PipeWire → Island/Control Centre | Volume, mute state | System API | Fixed |
| IF-09 | Backlight → Island/Control Centre | Brightness | System API | Fixed |
| IF-10 | MPRIS → Island | Now playing metadata, controls | D-Bus | Fixed |
| IF-11 | Power backend ↔ Quick Menu | List/set power mode | D-Bus / CLI | TBD-003 |
| IF-12 | Components → Popup Arbiter | `requestShow(surface, priority)`, `release(surface)` | in-process | TBD-010 |

## Shell action catalogue (IF-06)
Every action invocable by a keybind shall be listed here with a stable name.

| Action | Effect | Story |
|--------|--------|-------|
| `island.wallpaper` | Open wallpaper picker activity | US-01 |
| `theming.toggleColorSource` | Toggle wallpaper/custom colors | US-03 |
| `launcher.toggle` | Open/close launcher | US-04 |
| `keybindmenu.toggle` | Open/close keybind menu | US-05 |
| `dock.toggle` | Show/hide dock (persisted) | US-06 |
| `quickmenu.power` | Open power mode menu | US-08 |
| `brightness.step(+/-, size)` | Change brightness + show OSD | US-09 |
| `volume.step(+/-, size)` / `volume.mute` | Change volume + show OSD | US-10 |
