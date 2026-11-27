# C-13 — Quick Menu (reusable framework)

**Status:** Draft · **Build** (P3)

## Purpose
Generic centered list popup for choosing one option among a few. First consumer:
power modes (US-08). Future consumers may be added without changing the framework.

## Requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-QM-001 | A Quick Menu shall be defined by data: title, list of items (id, emoji/icon, label), current item, action callback. | I | Power menu is defined without framework code changes. |
| REQ-QM-002 | It shall appear centered on the focused monitor and take keyboard focus. | D | — |
| REQ-QM-003 | UP/DOWN shall move selection (wrap-around TBR-062), RETURN confirms, ESC/click outside closes (SYS-006). | T | — |
| REQ-QM-004 | Mouse hover shall move selection, click shall confirm. | D | — |
| REQ-QM-005 | The current item shall be marked (e.g. checkmark) and preselected on open. | D | — |
| REQ-QM-006 | The menu shall close after confirming and give feedback via Island (TBR-063). | D | — |
