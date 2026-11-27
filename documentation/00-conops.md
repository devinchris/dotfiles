# 00 — Concept of Operations (ConOps)

## 1. Purpose
Build a cohesive, keyboard-first, macOS-inspired desktop system on Hyprland for
daily productivity use on the User's laptop. The system shall feel like one product:
shared colors, shared motion, one place for settings, one registry for shortcuts.

## 2. Stakeholder
| Stakeholder | Interest |
|-------------|----------|
| User (Devin) | Daily driver for university and work; fast, beautiful, reliable after updates |

## 3. Scope
**In scope**
- Hyprland configuration (input, keybinds, window rules, animations)
- Shell UI: Top Bar incl. Control Centre, Dynamic Island, App Dock, Quick Menus, Settings App
- Theming engine (wallpaper-derived and custom colors) applied system-wide
- Integration of existing tools (launcher, terminal, power profiles)

**Out of scope (this baseline)**
- The separate macOS-like GNOME environment on the same machine
- Login/display manager, boot splash
- File search in the launcher (planned later, see US-04)
- Per-app volume mixer
- Multi-user support

## 4. Design principles
- **P1 Reuse before build.** Use existing, maintained tools where they meet the
  requirements (e.g. launcher backend, color generation, power profiles).
- **P2 Build what defines the identity.** Dynamic Island, Dock and Settings App are
  custom. Existing projects may be studied or forked (license permitting).
- **P3 Single source of truth.** Colors, keybinds, motion and user settings each live
  in exactly one place and are generated/propagated from there.
- **P4 Keyboard first, mouse complete.** Everything reachable by keyboard; all
  pointer interactions still work.
- **P5 Survive updates.** The system shall keep working after routine OS updates
  (see NFR-005).

## 5. Operational scenarios
- **OS-1 Morning start:** User logs in; bar, dock (if enabled) and wallpaper with
  matching colors appear. Launcher (SUPER+SPACE) opens apps instantly.
- **OS-2 Lecture:** User switches to the efficiency power mode (SHIFT+SUPER+P);
  fans stay quiet; adjusts brightness via F-keys, Dynamic Island shows the level.
- **OS-3 Personalisation:** User cycles wallpapers in the Dynamic Island
  (SUPER+SHIFT+W); all colors follow. Later locks colors to custom values
  (SUPER+SHIFT+B) picked in the Settings App.
- **OS-4 Learning shortcuts:** User opens the keybind menu (CTRL+SUPER+K), searches
  "dock", rebinds the toggle; the new shortcut works immediately.

## 6. Delivery phases
| Phase | Content | Stories |
|-------|---------|---------|
| P0 Foundation | Repo layout, theming engine, keybind registry, settings store, design tokens | US-02, SYS-* |
| P1 MVP | Top Bar (basic), launcher, terminal, input, volume/brightness via OSD fallback | US-04, US-07, US-11, US-09, US-10 |
| P2 Island | Dynamic Island + migration of volume/brightness/wallpaper picker | US-01, US-09, US-10, US-12 |
| P3 Dock & menus | App Dock, Quick Menu framework, power modes | US-06, US-08 |
| P4 Settings & polish | Settings App, custom color mode, keybind editor, Control Centre | US-03, US-05 |

Phase order is a proposal (TBR-001).
