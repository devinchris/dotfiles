# US-04 — Spotlight-like Launcher

| Field | Value |
|-------|-------|
| Status | Draft |
| Phase | P1 |
| Priority | Must |
| Components | C-20 Launcher |
| Depends on | IF-01 (theming), NFR-001 |
| Keybinds | KB-03 (SUPER+SPACE, TBD-014) |

## Stakeholder need
As the User, I want to quickly search apps and open them with RETURN. Speed and
accuracy of finding apps are the highest priority. File search may be added later.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-LCH-001 | KB-03 shall toggle the launcher, centered on the focused monitor, with the input focused. | D | Typing immediately enters the query. |
| REQ-LCH-002 | The launcher shall index all apps with a desktop entry visible to the user (XDG). | T | Count equals non-hidden .desktop entries. |
| REQ-LCH-003 | Newly installed apps shall be findable without restarting the launcher or session, ≤ 5 s after installation (TBR-035). | T | Install app → searchable. |
| REQ-LCH-004 | Matching shall be fuzzy and typo-tolerant, matching name, generic name and keywords. | T | "frefox" finds Firefox. |
| REQ-LCH-005 | Ranking shall prefer frequently/recently launched apps for equal match quality. | T | — |
| REQ-LCH-006 | Each result shall show the app's icon from the active icon theme with fallback icon. | D | No missing icons in default app set. |
| REQ-LCH-007 | RETURN launches the top/selected result; UP/DOWN move selection; ESC closes. | T | — |
| REQ-LCH-008 | The launcher shall meet NFR-001 and use the active palette. | T, D | — |
| REQ-LCH-009 | The architecture shall allow adding file search later without replacing the launcher (extensible providers). | A | ADR documents extension path. |

## Implementation notes
Reuse per P1. Candidates to evaluate in an ADR: walker, anyrun, fuzzel, vicinae, or a
Quickshell-native launcher. Criteria: latency, fuzzy quality, theming via IF-01,
plugin/provider model, maintenance status.

## Out of scope (this baseline)
File search, calculator, web search.
