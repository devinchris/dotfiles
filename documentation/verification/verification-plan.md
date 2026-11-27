# Verification Plan

## 1. Methods
| Code | Method | Typical use here |
|------|--------|------------------|
| T | Test — automated, repeatable, in `tests/` | logic (snapping, palette determinism, generator), IPC actions, persistence |
| D | Demonstration — manual, observed; documented with steps and a screenshot/recording | animations, look & feel, layout |
| I | Inspection — review of code/config | token usage, no hard-coded values, single source of truth |
| A | Analysis — documented reasoning/measurement | hardware feasibility (fans), performance budgets |

## 2. Test levels (V-model)
| Level | Verifies | Where |
|-------|----------|-------|
| Unit | Pure logic (step snapping, palette cache, registry validation) | `tests/unit/` |
| Integration | Component ↔ service via interfaces (IF-xx), invoked through CLI actions (SYS-010) | `tests/integration/` |
| System | End-to-end scenarios OS-1 … OS-4 from 00-conops | `tests/system/` + manual checklist |
| Acceptance | Owner sign-off on D-verified and subjective requirements (e.g. REQ-INP-001) | `verification/acceptance-log.md` |

## 3. Test environment
- **Nested Hyprland session** (Hyprland started inside the running session) for
  integration/system tests without disturbing the main session (TBR-070).
- Screenshots via `grim` for visual regression of static states (optional, TBR-071).
- Hardware-dependent tests (backlight, fans, touchpad) only on the target device;
  mark them `@hardware`.
- Test commands: `make test` (unit+integration), `make test-system` (TBR-072).

## 4. Standard test cases
| ID | Description | Covers |
|----|-------------|--------|
| VT-KB-01 | Spec table 06 and registry file contain the same bindings | REQ-KBR-003 |
| VT-KB-02 | No duplicate key combinations in registry | REQ-KBR-002 |
| VT-THM-01 | Palette A→B→A identical | REQ-THM-002 |
| VT-VOL-01 | Step/snap table for 0…100 % with 5 % and 2 % | REQ-VOL-001/002 |
| VT-PER-01 | Settings persist across shell restart | SYS-004 |
| VT-NFR-01 | Launcher open latency measurement | NFR-001 |

## 5. Acceptance log
D-verified requirements are recorded in `verification/acceptance-log.md` with date,
requirement ID, result (pass/fail), note.
