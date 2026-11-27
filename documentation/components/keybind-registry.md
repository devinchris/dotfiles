# C-02 — Keybind Registry

**Status:** Draft · **Build** (P0)

## Data model (per binding)
| Field | Type | Example |
|-------|------|---------|
| `id` | string, stable | `KB-05` |
| `keys` | list of key names | `["CTRL","SUPER","D"]` |
| `default` | list of key names | same as `keys` initially |
| `action` | shell action (IF-06) or Hyprland dispatcher | `dock.toggle` |
| `description` | string | "Show/hide dock" |
| `category` | string | "Dock" |
| `locked` | bool | `false` |

File format (TOML/JSON/YAML) → ADR (TBD-009).

## Requirements
| ID | Requirement | Verif. |
|----|-------------|--------|
| REQ-KBR-001 | A generator shall produce the Hyprland bind config from the registry; output goes to a `generated/` file sourced by hyprland.conf. | T |
| REQ-KBR-002 | The generator shall fail with a clear error on duplicate key combinations or unknown actions, and shall not overwrite the last valid output. | T |
| REQ-KBR-003 | Spec table `06-keybinds.md` and the registry shall be consistent (test VT-KB-01). | T |
| REQ-KBR-004 | User changes shall be stored as overrides of `default`, so that defaults can be updated in the repo without losing user changes (TBR-066). | T |
