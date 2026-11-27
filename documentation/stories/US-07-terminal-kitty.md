# US-07 — Terminal Emulator kitty

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P1 |
| Priority | Must |
| Components | C-21 Terminal |
| Depends on | IF-01 |
| Keybinds | KB-06 (SUPER+RETURN) |

## Stakeholder need
As the User, I want kitty as my terminal, configured like ML4W, but showing Arch ASCII
art instead of the ML4W logo, opened with SUPER+RETURN.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-TRM-001 | kitty shall be the default terminal for all system actions that open a terminal. | I | — |
| REQ-TRM-002 | KB-06 shall open a new kitty window. | D | — |
| REQ-TRM-003 | kitty config shall equal the ML4W reference config (pinned commit, TBD-006) except for deviations listed in this story. | I | Diff against reference shows only listed deviations. |
| REQ-TRM-004 | The greeting shall show Arch Linux ASCII art instead of the ML4W logo (via the fetch tool used by ML4W, TBD-028). | D | — |
| REQ-TRM-005 | kitty colors shall come from the active palette (REQ-THM-005). Deviation from ML4W: allowed. | D | — |

## Note
The reference config shall be copied into `reference/ml4w/kitty/` so agents need no
network access.
