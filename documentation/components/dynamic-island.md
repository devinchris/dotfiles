# C-11 — Dynamic Island

**Status:** Draft · **Build** (P2) · Inspiration: iPhone Dynamic Island, Alcove (macOS)

## Purpose
Pill-shaped element centered in the Top Bar that expands to host Island Activities.

## Hosted activities
| Activity | Story | Trigger | Interactive |
|----------|-------|---------|-------------|
| Wallpaper picker | US-01 | KB-01 | yes (keyboard focus) |
| Brightness OSD | US-09 | KB-08/09 | optional (TBR-042) |
| Volume OSD | US-10 | KB-10/11/12 | optional |
| Color source feedback | US-03 | KB-02 | no (TBR-034) |
| Now playing | US-12 | TBD | TBD |

## Requirements
| ID | Requirement | Verif. | Acceptance criterion |
|----|-------------|--------|----------------------|
| REQ-ISL-001 | In idle state the Island shall be a collapsed pill of size TBR-050 centered in the Top Bar. | D | — |
| REQ-ISL-002 | On activation it shall expand smoothly to the size required by the activity's content (`easing.spring`, `motion.normal`). | D | No content clipping during animation. |
| REQ-ISL-003 | Switching between activities while expanded shall morph directly to the new size without collapsing first. | D | — |
| REQ-ISL-004 | The Island shall collapse when (a) clicking outside, (b) ESC, (c) the activity reports `done`, or (d) 10 s without interaction. | T | Each condition triggers collapse. |
| REQ-ISL-005 | Interaction — pointer click/drag on the Island, arrow keys while focused, or repeated trigger keybind — shall reset the 10 s timer. | T | Volume key at t=9 s → stays open until t≥19 s. |
| REQ-ISL-006 | Non-interactive OSD activities shall use a shorter timeout (TBR-051, proposal 1.5 s) and shall not take keyboard focus. | T | Typing in an app continues during volume OSD. |
| REQ-ISL-007 | Interactive activities shall take keyboard focus and release it on collapse. | T | — |

## Priorities (Popup Arbiter rules)
| Situation | Behaviour |
|-----------|-----------|
| OSD triggered while an interactive activity is open | Show OSD as a compact overlay/secondary pill without closing the interactive activity (TBR-052) |
| Interactive activity triggered while another is open | Replace it |
| Launcher/Quick Menu/Keybind Menu opened while interactive activity open | Island collapses; new surface gets focus |
| Same trigger pressed again while its activity is open | Toggle closed (TBR-053) |

## Open points
TBR-050 … TBR-053, idle content (clock? media?) → TBD-037.
