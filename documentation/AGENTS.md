# AGENTS.md — Rules for planning and implementation agents

## 1. Reading order
1. `README.md` (ID scheme, status values)
2. `02-glossary.md` — terms are binding; do not invent synonyms
3. `00-conops.md`, `01-environment.md`
4. `03-architecture.md`, `04-interfaces.md`, `07-system-requirements.md`
5. Only then the specific `stories/US-xx-*.md` and `components/*.md` you work on

Load only the files relevant to the current task beyond steps 1–4.

## 2. Normative language
- **shall** = mandatory requirement, **should** = recommended, **may** = optional.
- Text marked *Rationale* or *Note* is informative, not a requirement.
- Requirements in `archive/` are **not** normative.

## 3. Handling gaps (most important rule)
- Never silently invent a value marked `TBD` or `TBR`. Either
  (a) ask the owner, or
  (b) use the proposed value given in `open-questions.md`, keep it configurable,
      and list it in your hand-off report as an assumption.
- If a requirement is ambiguous or contradicts another, **stop and report**
  (IDs of both requirements). Do not resolve it by guesswork.
- New requirements discovered during work go into `open-questions.md` as a
  proposal, never directly into an `Approved` requirement.

## 4. Roles
**Planning agent**
- Produces/updates `03-architecture.md`, `04-interfaces.md` and ADRs in `decisions/`.
- Every technology choice requires an ADR (options, criteria, decision, consequences).
- Produces an implementation plan ordered by the phases in `00-conops.md §6`.

**Implementation agent**
- Works on one story or one component at a time.
- References requirement IDs in commit messages, e.g. `feat(volume): step sizes [REQ-VOL-002]`.
- Writes tests per `verification/verification-plan.md` and updates the RTM
  (`verification/rtm.md`) status column.

## 5. Definition of Done (per requirement)
- [ ] Implemented exactly as specified; deviations documented and approved
- [ ] Verified by the method stated in the requirement (T/D/I/A)
- [ ] RTM row updated (`Implemented` → `Verified`)
- [ ] All values that the User may want to change are read from config, not hard-coded
- [ ] Colors, motion and shapes come from the design tokens (`05-design-system.md`)
- [ ] Keybinds come from the keybind registry (`06-keybinds.md`, SYS-003)
- [ ] No regressions in previously verified requirements

## 6. Boundaries
- Do not modify files outside the dotfiles repository.
- Do not change system-level packages, kernel parameters, or firmware/EC settings
  (relevant for power/fan control) without explicit owner approval.
- Do not edit `Approved` requirements; propose changes via `open-questions.md`.
- Do not delete anything in `archive/` or `decisions/`; supersede instead.

## 7. Hand-off report (end of every task)
1. Requirement IDs addressed and their new status
2. Assumptions made (with TBD/TBR IDs)
3. Open problems / newly discovered questions
4. How to verify manually (commands, keybinds to press)
