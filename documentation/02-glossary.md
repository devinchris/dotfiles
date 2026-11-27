# 02 — Glossary (binding)

Use exactly these terms in code, docs and commit messages.

| Term | Definition | Code identifier (suggested) | Do NOT call it |
|------|-----------|------------------|----------------|
| **Top Bar** | Always-visible horizontal bar at the top edge; shows status (Wi-Fi, Bluetooth, time, date) and hosts the Dynamic Island in its center | `topbar` | upper dock, standard upper dock, panel |
| **Dynamic Island** | Pill-shaped element centered in the Top Bar that expands to host transient content (OSDs, pickers, media). Inspired by iPhone Dynamic Island and Alcove | `island` | dynamic dock, notch |
| **Island Activity** | One piece of content the Island can show (e.g. volume, brightness, wallpaper picker, now playing) | `IslandActivity` | widget, mode |
| **App Dock** | Bar at the bottom edge with pinned and running apps | `dock` | lower dock, taskbar |
| **Control Centre** | macOS-style dropdown panel opened from the Top Bar with toggles and sliders | `controlcentre` | quick settings |
| **Quick Menu** | Centered, keyboard-navigable list popup for choosing among a few options (e.g. power modes) | `quickmenu` | popup, rofi menu |
| **Launcher** | Spotlight-like search for apps (later files) | `launcher` | spotlight, search |
| **Settings App** | Window/widget hosting all user-configurable settings of this system | `settings` | config menu |
| **Keybind Menu** | Searchable overlay listing all shortcuts, with editing | `keybindmenu` | cheatsheet |
| **Theming Engine** | Service that derives/holds the active color palette and propagates it | `theming` | pywal |
| **Palette** | Set of color roles (see 05-design-system) currently active | `palette` | colors, theme |
| **Color Source** | Where the palette comes from: `wallpaper` or `custom` | `colorSource` | color mode |
| **Settings Store** | Persistent storage of all user settings | `store` | config |
| **Keybind Registry** | Single data file defining all shortcuts, from which Hyprland config is generated | `keybinds` | keymap |
| **OSD** | On-screen display feedback for a value change (volume, brightness) | `osd` | notification |
| **Power Mode** | Named profile affecting CPU/GPU performance, fan behavior, sleep timers | `powerMode` | power plan |
| **User** | The person operating the system | — | "I" |
