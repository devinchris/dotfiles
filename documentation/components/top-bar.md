# C-10 — Top Bar & Control Centre

**Status:** Draft · **Build** (basic in P1, Control Centre in P4)

## Top Bar requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-BAR-001 | The Top Bar shall always be visible at the top edge of each monitor (TBR-060: all or focused only) and reserve space (exclusive zone). | D | Windows never overlap it. |
| REQ-BAR-002 | It shall show at least: Wi-Fi state, Bluetooth state, date, time. Further items (battery, workspaces, power mode, tray): TBD-038. | D | — |
| REQ-BAR-003 | The Dynamic Island shall be centered in the bar. | D | — |
| REQ-BAR-004 | Clicking Wi-Fi shall open a Wi-Fi menu listing networks with connect/disconnect. | D | — |
| REQ-BAR-005 | Clicking Bluetooth shall open a Bluetooth menu listing devices with connect/disconnect. | D | — |
| REQ-BAR-006 | Clicking date/time: TBD-039 (calendar popup?). | — | — |
| REQ-BAR-007 | A Control Centre icon shall open the Control Centre. | D | — |
| REQ-BAR-008 | Time format and layout (left/right item order): TBD-040. | — | — |

## Control Centre requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-CC-001 | The Control Centre shall be a dropdown panel anchored below its Top Bar icon, styled per 05 (`radius.panel`). | D | — |
| REQ-CC-002 | It shall contain: Wi-Fi toggle, Bluetooth toggle, brightness slider (REQ-BRT-006), volume slider (REQ-VOL-006). Additional tiles (DND, power mode, dock toggle, dark mode, media): TBD-041. | D | — |
| REQ-CC-003 | It shall be fully keyboard navigable (TAB/arrows, SPACE toggles). | D | — |
| REQ-CC-004 | It shall close per SYS-006. | D | — |
| REQ-CC-005 | A keybind to open it: TBD-042. | — | — |
