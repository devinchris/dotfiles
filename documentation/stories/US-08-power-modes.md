# US-08 — Power and Efficiency Modes

| Field | Value |
|-------|-------|
| Status | Draft — feasibility analysis required (TBD-005) |
| Phase | P3 |
| Priority | Should |
| Components | C-13 Quick Menu, C-22 Power backend |
| Depends on | IF-11, SYS-005 |
| Keybinds | KB-07 (SUPER+SHIFT+P) |

## Stakeholder need
As the User, I want to switch between power modes that change power consumption and
fan noise, affecting auto sleep/hibernate, CPU+GPU performance and fan curve, but not
brightness, through a quick menu navigated with UP/DOWN, with names and emojis.

## Derived requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-PWR-001 | KB-07 shall open the power mode Quick Menu with the active mode preselected. | D | — |
| REQ-PWR-002 | Each entry shall show an emoji to the left of the mode name. | D | — |
| REQ-PWR-003 | UP/DOWN shall move the selection, RETURN applies, ESC closes without change. | T | — |
| REQ-PWR-004 | The set of modes shall be: TBD-029 (proposal: 🔋 Efficiency, ⚖️ Balanced, ⚡ Performance). | — | — |
| REQ-PWR-005 | Applying a mode shall set the CPU/GPU performance profile of that mode. | T | Backend reports selected profile. |
| REQ-PWR-006 | Each mode shall define idle timeouts for screen off, suspend and hibernate (values TBD-030). | T | Idle daemon config matches mode. |
| REQ-PWR-007 | Each mode shall define fan behavior **if** the hardware exposes fan control (A: TBD-005); otherwise the requirement is withdrawn for this device. | A | Analysis result documented. |
| REQ-PWR-008 | Applying a mode shall not change display brightness. | T | Brightness identical before/after. |
| REQ-PWR-009 | The active mode shall persist across reboot and be visible in the Top Bar/Control Centre (TBR-040). | T, D | — |
| REQ-PWR-010 | Automatic switching on AC/battery change: TBD-031. | — | — |

## Implementation notes
Backend candidates: power-profiles-daemon / tuned-ppd (profiles), hypridle (timeouts),
vendor platform profile via `/sys/firmware/acpi/platform_profile` (often also drives
fans on Lenovo devices — to be confirmed by analysis).
