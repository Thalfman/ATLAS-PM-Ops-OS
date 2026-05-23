# MAINTENANCE_PLAN.md

## Artifact identity

- **Backlog ID:** A-0065
- **Phase:** 12 - Final Operating System Review
- **Parent file:** `12_FINAL_REVIEW/FINAL_OPERATING_SYSTEM_REVIEW.md`
- **Sibling files:** `12_FINAL_REVIEW/GAP_LIST.md`, `12_FINAL_REVIEW/OPERATING_RHYTHM.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

The plan for how ATLAS gets refreshed, retired, or migrated over time. ATLAS is now in maintenance mode (D-0062); this plan names who owns maintenance, how often it happens, what triggers an out-of-cadence revision, and what retirement looks like.

## Governance envelope

- **Data category:** Tom-personal.
- **Tool environment:** ATLAS-local Markdown.
- **Review intensity:** Standard at major transitions; Light for routine reviews.
- **Per-domain review pattern:** Status and reporting outputs.

## Maintenance owner

Tom owns ATLAS maintenance. There is no co-owner because ATLAS is personal preparation. When ATLAS artifacts are migrated to an employer venue (per Phase 11), the migrated copies pick up an employer-named accountable owner; the personal version stays Tom-owned in this repo.

## Cadences (reference; `OPERATING_RHYTHM.md` is authoritative)

- **Weekly:** small updates as observations land; commit-as-you-go.
- **Monthly:** gap list review, decision log scan, skill files check, synthetic demo touch.
- **Quarterly:** operating-system retrospective; migration readiness re-check; governance re-read; final-review re-validation.
- **Annually:** phase reflection; migration audit (if any migrations occurred); maintenance plan revision.

## What gets refreshed

### Routinely

- Decision log entries (append-only; retired decisions get marked Retired, never deleted).
- Backlog row notes (status flips, file paths, cross-references).
- Master context "current build stage" and "Immediate objective" (these now read "maintenance mode" rather than "Phase N - complete").
- Session handoff (after every session that touches files).
- Synthetic demo content (when a pattern sharpens during onboarding observations).

### On trigger

- Governance bundle (when employer policy becomes known or a near-miss surfaces a new pattern).
- Workflow / prompt card §14 migration notes (when a new tool gets approved).
- Templates (when a fillable shape needs sharpening — typically after first real use during onboarding).
- First-week kit (when manager / peer feedback indicates a missing or oversized question bank).

## What gets retired

Retirement is a first-class action, not a deletion. Per the `KNOWLEDGE_BASE_PATTERN.md` discipline:

- Backlog rows get marked `Deferred` or `Retired - see A-NNNN` (D-0017). IDs are append-only.
- Workflow cards get marked Status `Deferred` in their identity header (D-0030). IDs are append-only.
- Prompt cards get marked Status `Deferred` (D-0035). IDs are append-only.
- Decisions get marked Status `Retired` with a one-line rationale; the entry stays in the log.
- Files do not get deleted from `git` history; if a file truly belongs out of the working tree, move it to a `99_RETIRED/` directory (created on first need) with a Markdown stub explaining the retirement.

## What gets added

ATLAS is build-complete. New additions should be rare and follow this discipline:

1. **Trigger check.** Is the addition responding to an observed gap, an approval that changes posture, or a new safety constraint? If it is "this would be nice," reconsider.
2. **Schema fit.** A new workflow card uses the 16-section schema (D-0029, D-0034). A new prompt card uses the 14-section schema (D-0036). A new template gets the governance-envelope header per D-0042.
3. **ID assignment.** A new backlog row gets the next A-ID (append-only). A new workflow card gets the next W-NN; a new prompt card gets the next P-NN.
4. **Index update.** The relevant library / pack / kit index (`WORKFLOW_LIBRARY.md`, `PROMPT_LIBRARY.md`, `SYNTHETIC_DEMO_PACK.md`, `FIRST_WEEK_READINESS_KIT.md`) gets a new row.
5. **Decision log.** If the addition reflects a durable choice (new pattern, new constraint, new utility), log it.
6. **Branch and PR.** A `chore/<slug>` branch for housekeeping or a `feat/phase-NN-<slug>` if reopening a phase. PR against `main`.

## Triggers that warrant an out-of-cadence revision

- Employer policy becomes known and changes a posture assumption.
- A safety-boundary near-miss occurs (something almost went into an unapproved tool).
- A migration is authorized for the first time; the readiness checklist and rollback note get exercised against real data.
- A Codex review surfaces a durable rule.
- An onboarding observation invalidates a kit assumption (e.g., the discovery script's audience split needs adjustment).
- A phase deliverable that was deferred (A-0038 W-16, A-0029 skill refresh) gets picked up.

## When to declare ATLAS retired

ATLAS is a personal-preparation operating system. It retires when:

- Tom is no longer in a PM/Ops role for which ATLAS is preparation. The retirement converts ATLAS to an archive: a Markdown stub at the repo root, history preserved, no further updates.
- A successor system replaces ATLAS. The retirement marks ATLAS `Retired - see <successor>` in a final decision log entry; the successor is referenced from the master context.

Retirement is not "delete the repo." The repo's history is the audit trail for the personal-preparation discipline; that history stays.

## Branch and commit discipline (carryover from CLAUDE.md)

- Maintenance changes happen on `chore/<slug>` branches.
- Phase reopens (e.g., to land A-0038) happen on `feat/phase-NN-<slug>` branches.
- Never edit `main` directly.
- Conventional Commits, imperative present tense.
- Push and open a PR (ready-for-review).
- Decision log entries appended in the same session that introduces a durable rule.

## What this plan does not do

- Does not authorize any employer-data work. That gate stays in `11_MIGRATION/`.
- Does not commit Tom to any specific maintenance schedule under stress. The cadences are defaults; real life takes precedence.
- Does not require ongoing AI sessions. Maintenance can run entirely manually.
- Does not require a successor planning artifact at the time of retirement. If a successor exists, the retirement names it; if not, the retirement is clean.

## Cross-references

- Parent file: `12_FINAL_REVIEW/FINAL_OPERATING_SYSTEM_REVIEW.md`.
- Sibling files: `12_FINAL_REVIEW/GAP_LIST.md`, `12_FINAL_REVIEW/OPERATING_RHYTHM.md`.
- Source-of-truth: `00_MASTER_CONTEXT/MASTER_CONTEXT.md`, `09_HANDOFFS/SESSION_HANDOFF.md`, `10_DECISION_LOG/DECISION_LOG.md`, `03_BACKLOG/ARTIFACT_BACKLOG.md`.
- Repo-level rules: `CLAUDE.md`.
- Governance bundle: `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md` and siblings.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0065.
