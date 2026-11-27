# 01 — Target Environment & Constraints

## 1. Primary target
| Item | Value | Status |
|------|-------|--------|
| Device | Lenovo Yoga Pro 7a 15" (15ASH11) | Fixed |
| CPU/GPU | AMD Ryzen AI Max+ 388, integrated Radeon graphics | Fixed |
| Display | Built-in OLED, touch; resolution/refresh/scale → TBD-001 | Partly open |
| Input | Haptic touchpad (built-in), keyboard with F-keys; external mouse occasionally | Fixed |
| OS | CachyOS (Arch-based), rolling release | Fixed |
| Compositor | Hyprland, version → TBD-002 (pin a minimum version) | Open |
| Audio | PipeWire (assumed CachyOS default) → TBR-002 | To review |
| Power | power-profiles-daemon or tuned-ppd → TBD-003 | Open |
| Dotfiles management | GNU Stow | Fixed |
| Widget framework | See ADR-0001 (owner preference: Quickshell) | Proposed |

## 2. Secondary target (optional)
Desktop PC (Fedora KDE, AMD RX 9070 XT, dual monitor). Support is **not required**
in this baseline (TBD-004). Components shall nevertheless not hard-code single-monitor
assumptions (SYS-007).

## 3. Constraints
- **C1** No proprietary/closed-source components unless no alternative exists.
- **C2** Fan control depends on what the device firmware exposes. Requirements on
  fan curves (US-08) are conditional on feasibility analysis (TBD-005).
- **C3** Haptic touchpad click force is currently not adjustable on Linux on this
  device; it is out of scope.
- **C4** Packages shall come from official CachyOS/Arch repos or the AUR; every
  dependency is listed in a single manifest (SYS-009).
- **C5** The system shall be installable from the dotfiles repo by one documented
  script/procedure on a fresh CachyOS install.

## 4. Reference material
| Reference | Use | Status |
|-----------|-----|--------|
| ML4W dotfiles (kitty config) | Baseline for US-07 | Pin repo URL + commit → TBD-006 |
| Alcove (macOS notch app) | Visual/behavioral inspiration for Dynamic Island | Screenshots/videos → `assets/` (TBD-007) |
| macOS Dock & Control Centre | Inspiration for dock and control centre | Screenshots → `assets/` |

*Note:* agents may not have internet access. Reference material that matters shall be
copied into `assets/` or `reference/` in the repo.
