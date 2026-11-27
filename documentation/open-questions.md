# Open Questions — TBD / TBR Register

- **TBD** = value/decision unknown → must be decided before the affected requirement is `Approved`.
- **TBR** = proposed value exists → agents may use the proposal (configurable) and report it.
- **Decides:** O = Owner (preference/need), P = Planning agent (technical, via ADR; owner confirms).

## Environment & architecture
| ID | Question | Proposal | Decides | Affects |
|----|----------|----------|---------|---------|
| TBD-001 | Display resolution, refresh rate, scale factor of the built-in OLED | read from `hyprctl monitors` | O | 01, NFR-003 |
| TBD-002 | Minimum Hyprland version to pin | current CachyOS version at P0 start | P | 01 |
| TBD-003 | Power profile backend (power-profiles-daemon vs tuned-ppd) and its interface | whatever CachyOS ships | P | IF-11, US-08 |
| TBD-004 | Must the desktop PC (Fedora, dual monitor) be supported? | No (this baseline) | O | 01 |
| TBD-005 | Feasibility analysis: which fan/platform controls does the Yoga Pro 7a expose on Linux? | Analysis via `platform_profile`, hwmon | P | REQ-PWR-007 |
| TBD-006 | ML4W reference: repo URL + commit for kitty config | latest release, copied to `reference/` | O | US-07 |
| TBD-007 | Visual references (Alcove, macOS Dock/Control Centre) as screenshots/videos | add to `assets/` | O | C-11, C-12 |
| TBD-008 | Palette distribution mechanism (files + signal format) | generated files + IPC signal | P | IF-01, IF-02 |
| TBD-009 | Keybind registry file format and generator | TOML + small generator script | P | IF-03, IF-04 |
| TBD-010 | Shell IPC mechanism for actions and arbiter | framework-native IPC (ADR-0001) | P | IF-06, IF-12 |
| TBD-011 | Settings Store format and change notification | TOML/JSON + file watch | P | IF-07 |
| TBD-012 | Light and dark variants, or dark only? | dark only first | O | 05 §3 |
| TBD-013 | UI font family | — | O | 05 §4 |
| TBD-017 | Window-management keybinds (focus/move/workspaces) — adopt ML4W's or define new? | adopt ML4W set into registry | O | 06 |
| TBD-046 | Qt theming route (qt6ct / Kvantum) | qt6ct | P | C-01 |
| TBR-001 | Phase order P0–P4 | as in 00 §6 | O | 00 |
| TBR-002 | Audio stack is PipeWire | yes | P | IF-08 |
| TBR-003 | Repository layout | as in 03 §4 | P | 03 |

## Keybinds
| ID | Question | Proposal | Decides | Affects |
|----|----------|----------|---------|---------|
| TBD-014 | Launcher key: SUPER+SPACE or CTRL+SUPER+SPACE; conflict check against defaults | SUPER+SPACE | O | KB-03 |
| TBD-015 | Brightness step sizes (normal / with SHIFT) | 5 % / 2 % (same as volume) | O | KB-08/09, REQ-BRT-001/002 |
| TBD-016 | Media keys behaviour | play/pause/next/prev via MPRIS | O | KB-13 |
| TBR-013 | Mute key toggles mute; volume keys unmute | yes | O | KB-12, REQ-VOL-005 |

## Stories
| ID | Question | Proposal | Decides | Affects |
|----|----------|----------|---------|---------|
| TBD-020 | Wallpaper directory | `~/Pictures/Wallpapers` | O | REQ-WP-002 |
| TBD-021 | Live preview while browsing wallpapers? | no (apply on RETURN) | O | REQ-WP-005 |
| TBD-022 | Per-wallpaper manual override of generated colors? | not in this baseline | O | REQ-THM-006 |
| TBD-023 | How to derive full palette from two custom colors | generator seeded with primary; secondary overrides role | P | REQ-CCM-007 |
| TBD-024 | Which bindings are locked (non-editable)? | exit Hyprland, keybind menu itself | O | REQ-KBM-009 |
| TBD-025 | Downloads item: file manager to use; macOS-like stack preview? | open folder only | O | REQ-DCK-003 |
| TBD-026 | Dock click on app with multiple windows | cycle through windows | O | REQ-DCK-005 |
| TBD-027 | Dock: exclusive zone vs overlay, auto-hide | exclusive zone, no auto-hide | O | REQ-DCK-012 |
| TBD-028 | Fetch tool for ASCII greeting (fastfetch?) | as ML4W | P | REQ-TRM-004 |
| TBD-029 | Set of power modes and emojis | 🔋 Efficiency, ⚖️ Balanced, ⚡ Performance | O | REQ-PWR-004 |
| TBD-030 | Idle timeouts per mode (screen off / suspend / hibernate) | — | O | REQ-PWR-006 |
| TBD-031 | Auto-switch power mode on AC/battery | no | O | REQ-PWR-010 |
| TBD-032 | Brightness curve linear vs perceptual | perceptual | P | REQ-BRT-009 |
| TBD-033 | Allow volume > 100 %? | no | O | REQ-VOL-003 |
| TBD-034 | Output device switching (where, how) | later, in Control Centre | O | REQ-VOL-008 |
| TBD-035 | Touchpad acceleration curve definition | iterate with owner | O+P | REQ-INP-001 |
| TBD-036 | Natural scrolling / gestures | natural scrolling on touchpad only | O | REQ-INP-005 |
| TBD-037 | US-12 Now Playing — write the stakeholder need; Island idle content | — | O | US-12, C-11 |
| TBR-030 | Wallpaper carousel wraps around | yes | O | REQ-WP-003 |
| TBR-031 | Wallpaper pointer interaction | click select, double-click apply | O | REQ-WP-008 |
| TBR-032 | Palette propagation time | ≤ 1 s | O | REQ-THM-004 |
| TBR-033 | Color picker type | HSV area + hex input | O | REQ-CCM-004 |
| TBR-034 | Island feedback when toggling color source | yes, brief | O | REQ-CCM-006 |
| TBR-035 | New apps findable delay | ≤ 5 s | O | REQ-LCH-003 |
| TBR-036 | Read-only keybind menu already in P1 | yes | O | US-05 |
| TBR-037 | Reorder pinned apps by drag & drop | yes | O | REQ-DCK-007 |
| TBR-038 | Dock icon size range | 32–96 px | O | REQ-DCK-011 |
| TBR-039 | App name tooltip on hover | yes | O | REQ-DCK-013 |
| TBR-040 | Show active power mode in bar / Control Centre | Control Centre only | O | REQ-PWR-009 |
| TBR-041 | Minimum brightness | 1 % | O | REQ-BRT-003 |
| TBR-042 | Island OSD slider adjustable by drag/arrows | yes | O | REQ-BRT-005 |
| TBR-043 | External mouse default acceleration | flat | O | REQ-INP-002 |

## Components & design
| ID | Question | Proposal | Decides | Affects |
|----|----------|----------|---------|---------|
| TBD-038 | Further Top Bar items (battery, workspaces, tray, power mode) | battery + workspaces | O | REQ-BAR-002 |
| TBD-039 | Click on date/time | calendar popup | O | REQ-BAR-006 |
| TBD-040 | Time format, item order in bar | 24 h; left workspaces, right status | O | REQ-BAR-008 |
| TBD-041 | Additional Control Centre tiles | DND, power mode, dock toggle, media | O | REQ-CC-002 |
| TBD-042 | Keybind for Control Centre | — | O | REQ-CC-005 |
| TBD-043 | Scope of "basic device settings" in Settings App | display scale, sound output, Wi-Fi, Bluetooth | O | C-14 |
| TBD-044 | Settings App window type | floating window | P | REQ-SET-005 |
| TBD-045 | Keybind for Settings App | — | O | REQ-SET-006 |
| TBR-010 | Motion tokens (durations, easing) | as in 05 §1 | O | 05 |
| TBR-011 | Shape & type tokens | as in 05 §2/§4 | O | 05 |
| TBR-012 | Key caps without "+" separators | yes | O | 05 §5 |
| TBR-050 | Collapsed Island size | — (from screenshot reference) | O | REQ-ISL-001 |
| TBR-051 | OSD timeout | 1.5 s | O | REQ-ISL-006 |
| TBR-052 | OSD during interactive activity: secondary pill | yes | O | C-11 priorities |
| TBR-053 | Same trigger again closes activity | yes | O | C-11 priorities |
| TBR-060 | Top Bar on all monitors or focused only | all | O | REQ-BAR-001 |
| TBR-061 | Downloads dock item non-removable | yes | O | C-12 |
| TBR-062 | Quick Menu wrap-around | yes | O | REQ-QM-003 |
| TBR-063 | Quick Menu confirmation feedback via Island | yes | O | REQ-QM-006 |
| TBR-064 | Settings apply live (no Apply button) | yes | O | REQ-SET-002 |
| TBR-065 | Searchable Settings App | yes | O | REQ-SET-004 |
| TBR-066 | Keybind user overrides stored separately from defaults | yes | P | REQ-KBR-004 |

## Non-functional & verification
| ID | Question | Proposal | Decides | Affects |
|----|----------|----------|---------|---------|
| TBR-020 | Performance budgets (100 ms launcher, 50 ms OSD, 300 MB/1 % idle, 200 ms picker) | as stated | O | NFR-001…004, REQ-WP-007 |
| TBR-021 | Manual steps allowed during install | ≤ 1 | O | NFR-007 |
| TBR-070 | Nested Hyprland as test environment | yes | P | verification plan |
| TBR-071 | Screenshot-based visual regression | optional | P | verification plan |
| TBR-072 | Test entry points (`make test`, `make test-system`) | yes | P | verification plan |
| TBR-080 | ADR-0001 criteria weights | as stated | O | ADR-0001 |
