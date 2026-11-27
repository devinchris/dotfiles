# 05 — Design System (tokens)

All UI shall use these tokens; no literal colors, durations or radii in component
code (SYS-002). Values marked TBR are proposals and must be configurable.

## 1. Motion
| Token | Use | Value |
|-------|-----|-------|
| `motion.fast` | hover, small state changes | 120 ms (TBR-010) |
| `motion.normal` | Island expand/collapse, menu open | 250 ms (TBR-010) |
| `motion.slow` | Dock morph in/out | 350 ms (TBR-010) |
| `easing.standard` | default | ease-out cubic (TBR-010) |
| `easing.spring` | Island expand | spring, slight overshoot (TBR-010) |

Rule: content inside the Island fades in only after the container reached ≥ 80 % of
its target size, to avoid clipped text (TBR-010).

## 2. Shape
| Token | Value |
|-------|-------|
| `radius.pill` | full (height/2) — Island collapsed, sliders |
| `radius.panel` | 16 px (TBR-011) — Control Centre, Quick Menu, Settings |
| `radius.key` | 6 px (TBR-011) — key caps in Keybind Menu |
| `spacing.unit` | 4 px; all spacing is a multiple |

## 3. Color roles (palette)
Provided by the Theming Engine (IF-01).
| Role | Use |
|------|-----|
| `primary` / `onPrimary` | accents, active slider fill, focused items |
| `secondary` / `onSecondary` | secondary accents, inactive indicators |
| `surface` / `onSurface` | panel backgrounds and text |
| `surfaceVariant` | dock background, key caps |
| `outline` | borders, Hyprland active border |
| `error` | errors, critical battery |
Light/dark: TBD-012.

## 4. Typography
Font family TBD-013. Sizes: `text.small` 11, `text.body` 13, `text.title` 16 (pt, TBR-011).

## 5. Key cap rendering (US-05)
- Each key is drawn as a cap: rounded rectangle, `radius.key`, `surfaceVariant` fill.
- Single-character keys: square cap. Modifier keys (SUPER, CTRL, SHIFT, ALT) and
  RETURN/SPACE: wider rounded rectangle.
- Keys of one shortcut are separated by a small gap, no "+" sign (TBR-012).
