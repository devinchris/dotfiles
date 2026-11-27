# C-12 — App Dock

**Status:** Draft · **Build** (P3)

All functional requirements are in [stories/US-06-app-dock.md](../stories/US-06-app-dock.md)
(REQ-DCK-001 … 013). This file holds component-level design only.

## Component notes
- Data sources: Hyprland IPC (IF-05) for windows; desktop entries for icons/names;
  Settings Store (IF-07) for pinned list, size, visibility.
- App identity: map windows to apps via window class ↔ desktop entry
  (`StartupWMClass` fallback rules → planning agent, documented in an ADR).
- The Downloads item is a special, non-removable item (TBR-061).
