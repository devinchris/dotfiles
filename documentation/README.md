# Hyprland Desktop System — Specification

**Document set version:** 0.2.0 (Draft baseline)
**Status:** Draft — not yet approved for implementation of components marked `Draft`
**Owner / sole stakeholder:** Devin (the "User")

This folder is the single source of truth for a complete desktop system built on
Hyprland (top bar, Dynamic Island, dock, quick menus, settings app, theming, input).
It is written for LLM agents that **plan** (architecture, framework choice) and
**implement** (code, tests). Humans can read it too.

## Document hierarchy (read top-down)

The structure follows a classic systems-engineering flow:
stakeholder needs → system requirements → architecture → component requirements →
interfaces → verification.

| # | Document | Purpose | Primary reader |
|---|----------|---------|----------------|
| — | [AGENTS.md](AGENTS.md) | Rules of engagement for agents | all agents |
| 00 | [00-conops.md](00-conops.md) | Vision, scope, operational scenarios, principles | planner |
| 01 | [01-environment.md](01-environment.md) | Target hardware/OS, constraints | planner, implementer |
| 02 | [02-glossary.md](02-glossary.md) | Binding terminology | all |
| 03 | [03-architecture.md](03-architecture.md) | Logical architecture, components, cross-cutting services | planner |
| 04 | [04-interfaces.md](04-interfaces.md) | Interface definitions (ICD) between components | planner, implementer |
| 05 | [05-design-system.md](05-design-system.md) | Motion, shape, color roles, typography | implementer |
| 06 | [06-keybinds.md](06-keybinds.md) | Central keybind registry (all shortcuts) | all |
| 07 | [07-system-requirements.md](07-system-requirements.md) | Cross-cutting (SYS) and non-functional (NFR) requirements | all |
| — | [stories/](stories/) | Stakeholder needs (US-xx) + derived requirements (REQ-…) | implementer |
| — | [components/](components/) | Per-component specification | implementer |
| — | [verification/](verification/) | Verification plan + requirements traceability matrix (RTM) | implementer, reviewer |
| — | [decisions/](decisions/) | Architecture Decision Records (ADR) | planner |
| — | [open-questions.md](open-questions.md) | TBD/TBR register | owner, planner |
| — | [CHANGELOG.md](CHANGELOG.md) | Baseline history | all |
| — | [archive/](archive/) | Superseded drafts — **not normative** | nobody |

## Identifier scheme

| Prefix | Meaning | Defined in |
|--------|---------|-----------|
| `US-nn` | Stakeholder need (user story) | `stories/` |
| `REQ-<AREA>-nnn` | Derived requirement for one story/component | `stories/`, `components/` |
| `SYS-nnn` | Cross-cutting system requirement | `07-system-requirements.md` |
| `NFR-nnn` | Non-functional requirement | `07-system-requirements.md` |
| `IF-nn` | Interface | `04-interfaces.md` |
| `ADR-nnnn` | Architecture decision | `decisions/` |
| `TBD-nnn` / `TBR-nnn` | Open value (to be determined / to be reviewed) | `open-questions.md` |

IDs are **stable**: never renumber, never reuse. Deleted items are marked `Withdrawn`.

## Status values

`Draft` → `Proposed` → `Approved` → `Implemented` → `Verified` (or `Withdrawn`).
Only `Approved` requirements may be implemented without asking the owner.
