# ADR-0001 — Widget / Shell Framework

| Field | Value |
|-------|-------|
| Status | **Proposed** — owner preference: Quickshell; planning agent to confirm against criteria |
| Date | 2026-11-26 |
| Deciders | Owner |
| Affects | C-10 … C-15, NFR-001 … 004, SYS-002, SYS-010 |

## Context
The custom components (Top Bar, Dynamic Island, App Dock, Quick Menus, Settings App,
Keybind Menu) need a framework for Wayland layer-shell UIs with fluid, size-morphing
animations, drag interactions (dock resize, sliders) and IPC.

## Decision criteria (weights proposal, TBR-080)
| Criterion | Weight | Source |
|-----------|--------|--------|
| Animation quality (size morph, springs) | 5 | REQ-ISL-002/003, REQ-DCK-008 |
| Performance / memory at idle | 4 | NFR-003, NFR-004 |
| Hyprland & system integration (IPC, PipeWire, MPRIS, NM, BlueZ) | 4 | IF-05, IF-08 … 10 |
| Stability across updates / maintenance activity | 4 | NFR-005 |
| CLI/IPC actions for testability | 3 | SYS-010 |
| Existing reference projects to learn from/fork | 3 | P2 |
| Owner's language familiarity | 2 | — |

## Options
| Option | Language | Notes |
|--------|----------|-------|
| Quickshell | QML (+ JS) | Owner preference; Qt Quick animation system; several public Hyprland shells built on it |
| AGS / Astal | TypeScript/GJS (GTK4) | Mature ecosystem, many service bindings |
| Fabric | Python (GTK3) | Python familiarity; smaller ecosystem |
| eww | Yuck/SCSS | Simple widgets; limited for complex morphing UI |

The planning agent shall fill pros/cons/score, ideally backed by a small prototype
of the Island expand/morph animation (REQ-ISL-002/003) in the top 2 options.

## Decision
Pending.

## Consequences
Pending.
