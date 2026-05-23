# OPERATING_RHYTHM.md

## Artifact identity

- **Backlog ID:** A-0064
- **Phase:** 12 - Final Operating System Review
- **Parent file:** `12_FINAL_REVIEW/FINAL_OPERATING_SYSTEM_REVIEW.md`
- **Sibling files:** `12_FINAL_REVIEW/GAP_LIST.md`, `12_FINAL_REVIEW/MAINTENANCE_PLAN.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

The steady-state cadence for using and maintaining ATLAS PM/Ops OS after Phase 12. This is the rhythm Tom runs against ATLAS in his actual work week — both during clearance-limited onboarding and after — not a new build schedule. Build sessions are now exceptions, not the norm.

## Governance envelope

- **Data category:** Tom-personal.
- **Tool environment:** ATLAS-local Markdown for the cadence definition; the actual practice runs in the appropriate venue (ATLAS, personal AI tool on synthetic, employer-approved tool when approved).
- **Review intensity:** Standard.
- **Per-domain review pattern:** Status and reporting outputs.

## Daily cadence (workdays)

Each workday, in any order:

- **Open ATLAS at session start** if doing personal-preparation work that touches workflows, prompts, or templates.
- **Use the first-week kit** during onboarding: discovery script (`FIRST_WEEK_DISCOVERY_SCRIPT.md`) tailored before meetings; listening plan (`LISTENING_PLAN.md`) end-of-day entry; sanitization filter on every entry.
- **No employer data into personal tools.** Confirm before sending anything to any AI tool: data category, tool environment, named reviewer.
- **Capture process gaps in neutral language** using the listening plan; when the gap deserves a structured note, use the (forthcoming) `W-16` process gap note workflow or a personal note.

## Weekly cadence (Fridays)

- **End-of-week summary** in the first-week kit (during onboarding) or in personal notes (after): what operating rhythms exist, where friction is, what to learn next.
- **Manager 1:1 prep**: tailor `WHAT_I_CAN_OFFER_THIS_WEEK.md` based on the week's commitments and listening-log themes; confirm scope discipline per D-0044.
- **Listening plan weekly reflection**: three to five themes from the week; one safe to raise at the next manager 1:1; one to watch for one more week.
- **Workflow / prompt / template use review**: did any ATLAS artifact get used this week against synthetic content? Did anything need to change? Log small adjustments in the artifact's own file; log durable changes in `DECISION_LOG.md`.

## Monthly cadence

- **Gap list review**: re-read `GAP_LIST.md`. Move any items that should now move. Close any items that are no longer relevant. Add new gaps observed during the month.
- **Decision log scan**: skim recent entries to confirm the durable picture is still accurate. Mark any retired decisions.
- **Skill files check**: do the three `skills/*/SKILL.md` files still match how Tom uses ATLAS? Schedule a refresh if not (A-0029 close-out).
- **Synthetic demo review**: pick one demo and walk it end-to-end. Confirm it still illustrates the pattern clearly; update if onboarding-period observations suggest a sharper framing.

## Quarterly cadence (Q1 / Q2 / Q3 / Q4)

- **Operating system retrospective**: ~30 minutes. Pick three things that worked, three things that need attention, one thing to retire. Log durable changes in `DECISION_LOG.md`.
- **Migration readiness re-check**: are any artifacts now candidates for real migration? If yes, the next migration runs the `PER_ARTIFACT_MIGRATION_READINESS_CHECKLIST.md` — one at a time, no shortcuts.
- **Governance bundle re-read**: re-read `06_GOVERNANCE/` files end-to-end. Confirm they still match Tom's posture. Any drift gets a logged decision.
- **Final review re-validation**: re-read `FINAL_OPERATING_SYSTEM_REVIEW.md` against current state. Note any verdicts that have changed.

## Annual cadence

- **Phase reflection**: read each `MASTER_PLAN.md` phase summary against actual use. Are there phases that should be retired or merged? Are there new phases that should exist?
- **Migration audit (if any migrations occurred)**: confirm rollback notes are current, owner roles are still accurate, audit trails are intact in the employer venue.
- **Maintenance plan revision**: update `MAINTENANCE_PLAN.md` based on the year's experience.

## On-trigger actions (not on a cadence)

- **A new tool is approved by the employer**: walk the six-step pattern from `AI_TOOL_APPROVAL_STRATEGY.md` for any artifact that wants to use the new tool. Update `EMPLOYER_MIGRATION_PLAN.md` if a posture changes.
- **A new data category surfaces**: update `DATA_SENSITIVITY_DECISION_MODEL.md` and back-port to any workflow / prompt that needs to refer to it.
- **A safety-boundary near-miss**: log a decision; update `AI_GOVERNANCE_NOTES.md` red flags if a new pattern emerged.
- **An artifact gets used against real data for the first time**: confirm the migration was approved through the checklist; confirm the audit trail in the employer venue.
- **A Codex review thread surfaces a durable rule**: log the decision; back-port to the relevant artifact's standing rules.

## How this rhythm interacts with build sessions

ATLAS is build-complete after Phase 12. Build sessions become exceptions. When a future session is a "build" session (e.g., to land A-0038 W-16 process gap note workflow, or to refresh skill files), the session-start protocol in `MASTER_CONTEXT.md` and the repo `CLAUDE.md` rules apply as usual: read source-of-truth, restate the safety boundary, open a `chore/<slug>` or `feat/phase-NN-<slug>` branch (whichever fits), commit small, push, PR.

Maintenance sessions (the common case) use the cadences above. They do not require a new feature branch unless they touch an ATLAS file; small reflective notes that stay in personal preparation are fine.

## Cross-references

- Parent file: `12_FINAL_REVIEW/FINAL_OPERATING_SYSTEM_REVIEW.md`.
- Sibling files: `12_FINAL_REVIEW/GAP_LIST.md`, `12_FINAL_REVIEW/MAINTENANCE_PLAN.md`.
- Source-of-truth: `00_MASTER_CONTEXT/MASTER_CONTEXT.md`, `09_HANDOFFS/SESSION_HANDOFF.md`.
- Kit: `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md` and its sub-files.
- Migration: `11_MIGRATION/` directory.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0064.
