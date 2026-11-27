# US-02 — Wallpaper-based Dynamic Colors

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P0 |
| Priority | Must |
| Components | C-01 Theming Engine |
| Depends on | SYS-001, IF-01 |
| Keybinds | — |

## Stakeholder need
As the User, I want the system colors, including primary and secondary accent, to be
derived automatically from my wallpaper and to update when the wallpaper changes.
The same wallpaper shall always yield the same colors.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-THM-001 | When color source is `wallpaper`, the Theming Engine shall derive a palette (all roles of 05 §3) from the active wallpaper. | T | All roles present in the generated output. |
| REQ-THM-002 | Palette derivation shall be deterministic: identical image content shall yield an identical palette. | T | Switching A → B → A yields byte-identical palette for A. |
| REQ-THM-003 | Palettes shall be cached keyed by image content hash. | T | Second application of a wallpaper does not invoke the generator. |
| REQ-THM-004 | On wallpaper change, all consumers (shell UI, kitty, Hyprland borders, GTK, Qt, launcher) shall reflect the new palette within 1 s (TBR-032) without restart of the session. | D, T | Visual check across consumers. |
| REQ-THM-005 | Running kitty windows shall update colors live. | D | Open kitty changes colors without reopening. |
| REQ-THM-006 | The User shall be able to override the generated primary/secondary of a specific wallpaper (TBD-022). | — | — |

## Implementation notes
- Generator candidates: matugen (Material You roles), wallust, pywal16 → ADR.
- Material-style role names match 05 §3 directly if matugen is chosen.

## Out of scope
Per-application custom themes beyond the listed consumers.
