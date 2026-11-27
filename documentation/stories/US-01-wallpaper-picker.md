# US-01 — Wallpaper Picker in the Dynamic Island

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P2 |
| Priority | Must |
| Components | C-11 Dynamic Island, C-01 Theming Engine |
| Depends on | US-02, SYS-005 |
| Keybinds | KB-01 (SUPER+SHIFT+W) |

## Stakeholder need
As the User, I want to change my wallpaper by cycling through the available wallpapers
like a carousel with the arrow keys, inside the Dynamic Island.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-WP-001 | KB-01 shall open the wallpaper picker as an Island Activity. | D | Pressing KB-01 expands the Island showing the picker. |
| REQ-WP-002 | The picker shall show thumbnails of all images in the wallpaper directory (TBD-020) as a horizontal carousel, with the current wallpaper preselected. | D | Current wallpaper is centered/highlighted on open. |
| REQ-WP-003 | LEFT/RIGHT shall move the selection by one; the carousel shall wrap around at the ends (TBR-030). | T | From last item, RIGHT selects the first. |
| REQ-WP-004 | RETURN shall apply the selected wallpaper; ESC shall close without change. | T | After RETURN wallpaper and palette change; after ESC nothing changes. |
| REQ-WP-005 | Whether moving the selection previews the wallpaper live before RETURN is TBD-021. | — | — |
| REQ-WP-006 | The applied wallpaper shall be persisted and restored on next login. | T | Reboot → same wallpaper. |
| REQ-WP-007 | Thumbnails shall be cached so that opening the picker with ≤ 200 wallpapers takes ≤ 200 ms after first generation (TBR-020). | T | Measured open time. |
| REQ-WP-008 | Pointer: clicking a thumbnail selects it; double-click or click on the selected one applies it (TBR-031). | D | — |

## Implementation notes
- Wallpaper daemon candidates: swww, hyprpaper (ADR needed; swww supports transitions).
- Island auto-close timeout per components/dynamic-island.md.

## Out of scope
Downloading wallpapers, video wallpapers.
