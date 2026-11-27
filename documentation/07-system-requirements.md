# 07 — System Requirements (cross-cutting & non-functional)

Verification method: **T** Test (automated) · **D** Demonstration (manual, observed) ·
**I** Inspection (code/config review) · **A** Analysis.

## Cross-cutting (SYS)
| ID | Requirement | Rationale | Verif. | Status |
|----|-------------|-----------|--------|--------|
| SYS-001 | The system shall have exactly one active palette at any time, provided by the Theming Engine; all themed consumers shall derive their colors from it. | P3 | I, T | Draft |
| SYS-002 | UI components shall not contain literal color, duration or radius values; they shall use design tokens (05). | Consistency, theming | I | Draft |
| SYS-003 | All keybinds shall be defined in a single keybind data file; the Hyprland bind config shall be generated from it. | US-05 editing; P3 | I, T | Draft |
| SYS-004 | All user-changeable settings shall be persisted in the Settings Store and survive logout and reboot. | US-03, US-06, US-11 | T | Draft |
| SYS-005 | At most one transient surface (Island activity, Quick Menu, Launcher, Keybind Menu) shall hold keyboard focus at a time; arbitration rules per components/dynamic-island.md. | Avoid focus conflicts | T, D | Draft |
| SYS-006 | Every transient surface shall close on ESC and on click outside. | Consistency | D | Draft |
| SYS-007 | Components shall appear on the monitor with the focused window; no hard-coded monitor names. | Multi-monitor robustness | I, D | Draft |
| SYS-008 | Every component shall log to the user journal with a component tag. | Debuggability | I | Draft |
| SYS-009 | All runtime dependencies shall be listed in one package manifest used by the install procedure. | C4, C5 | I | Draft |
| SYS-010 | All shell actions shall be invocable from the command line (IF-06), so they can be bound and tested independently of keybinds. | Testability | T | Draft |

## Non-functional (NFR)
| ID | Requirement | Verif. | Status |
|----|-------------|--------|--------|
| NFR-001 | The launcher shall be visible ≤ 100 ms after the keybind (TBR-020). | T | Draft |
| NFR-002 | An OSD shall reflect a volume/brightness key press ≤ 50 ms after the key event (TBR-020). | T | Draft |
| NFR-003 | Animations shall run at the display refresh rate without dropped frames under normal load (TBR-020). | D, A | Draft |
| NFR-004 | The idle shell (all components) shall use ≤ 300 MB RSS and ≤ 1 % CPU on average (TBR-020). | T | Draft |
| NFR-005 | After a routine system update, the system shall start without manual intervention; a startup self-check shall report missing dependencies or incompatible versions. | D | Draft |
| NFR-006 | If one component crashes, the others shall keep working and the crashed one shall be restarted automatically. | T | Draft |
| NFR-007 | The whole system shall be installable on a fresh CachyOS install via the documented procedure in ≤ 1 manual step besides running the installer (TBR-021). | D | Draft |
| NFR-008 | Every function shall be operable by keyboard alone. | D | Draft |
