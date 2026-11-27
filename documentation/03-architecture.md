# 03 — Logical Architecture

**Status:** Draft. The planning agent refines this document and records every
technology choice as an ADR. This file defines *what* the parts are and *how they
relate*, not *which library* implements them.

## 1. System context
```
           ┌──────────── User (keyboard, touchpad, mouse) ────────────┐
           ▼                                                          ▼
   ┌───────────────┐   keybind dispatch   ┌──────────────────────────────────┐
   │   Hyprland    │ ───────────────────▶ │            Shell (UI)            │
   │  compositor   │ ◀── window/ws IPC ── │ Top Bar · Island · Dock ·        │
   └───────┬───────┘                      │ Quick Menus · Control Centre ·   │
           │                              │ Settings App · Keybind Menu      │
           ▼                              └───────┬───────────────┬──────────┘
   System services:                               │               │
   PipeWire · backlight · power profiles ·        ▼               ▼
   NetworkManager · BlueZ · MPRIS          Core services (this project):
                                           Theming Engine · Keybind Registry ·
                                           Settings Store · Popup Arbiter
```

## 2. Components
| ID | Component | Build/Reuse | Spec | Stories |
|----|-----------|-------------|------|---------|
| C-01 | Theming Engine | Build (wraps existing generator) | components/theming-engine.md | US-01, US-02, US-03 |
| C-02 | Keybind Registry | Build | components/keybind-registry.md | US-05, all with KS |
| C-03 | Settings Store | Build | 03 §3.3 | all configurable |
| C-04 | Popup Arbiter | Build | 03 §3.4 | US-01, US-08, US-09, US-10 |
| C-10 | Top Bar | Build | components/top-bar.md | US-09, US-10 (Control Centre) |
| C-11 | Dynamic Island | Build | components/dynamic-island.md | US-01, US-09, US-10, US-12 |
| C-12 | App Dock | Build | components/app-dock.md | US-06 |
| C-13 | Quick Menu | Build | components/quick-menu.md | US-08 |
| C-14 | Settings App | Build | components/settings-app.md | US-03, US-05, US-11 |
| C-15 | Keybind Menu | Build | stories/US-05 | US-05 |
| C-20 | Launcher | Reuse/configure | components/launcher.md | US-04 |
| C-21 | Terminal (kitty) | Reuse/configure | stories/US-07 | US-07 |
| C-22 | Power Mode backend | Reuse | stories/US-08 | US-08 |

## 3. Cross-cutting services
### 3.1 Theming pipeline (C-01)
`wallpaper or custom colors → palette (cached) → templates → kitty, Hyprland borders,
GTK/Qt, shell UI, launcher`. Exactly one active palette at any time (SYS-001).

### 3.2 Keybind pipeline (C-02)
`keybinds data file → generated Hyprland bind config + data for Keybind Menu`.
Hand-written `bind =` lines outside the generated file are prohibited (SYS-003).

### 3.3 Settings Store (C-03)
One versioned, human-readable file (format → ADR) under `$XDG_CONFIG_HOME/<project>/`.
Holds: dock visibility & size, color source, custom colors, pointer settings,
pinned apps, power mode, etc. Components read on start and subscribe to changes.

### 3.4 Popup Arbiter (C-04)
Decides which transient surface is visible. Rules: see SYS-005 and
components/dynamic-island.md §Priorities.

## 4. Repository layout (proposal, TBR-003)
```
dotfiles/
├── documentation/          # this spec
├── hypr/                   # hyprland.conf + generated/ (do not edit generated/)
├── shell/                  # widget framework code (per ADR-0001)
├── theming/templates/      # one template per consumer app
├── keybinds/keybinds.<ext> # registry (SYS-003)
├── packages.txt            # dependency manifest (SYS-009)
├── install.sh
└── tests/
```
