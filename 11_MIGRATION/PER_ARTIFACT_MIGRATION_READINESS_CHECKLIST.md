# PER_ARTIFACT_MIGRATION_READINESS_CHECKLIST.md

## Artifact identity

- **Backlog ID:** A-0060
- **Phase:** 11 - Employer Migration Plan
- **Parent file:** `11_MIGRATION/EMPLOYER_MIGRATION_PLAN.md`
- **Sibling file:** `11_MIGRATION/MIGRATION_ROLLBACK_NOTE.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A fillable checklist Tom runs per artifact before any migration from ATLAS to an employer-approved venue. The checklist forces every gate from the parent migration plan to be answered explicitly. A "no" or "unclear" anywhere is a stop, not a flag for "we'll figure it out later."

## Governance envelope

- **Data category:** Tom-personal for the checklist itself.
- **Tool environment:** ATLAS-local Markdown for the checklist; the actual migration takes place in the employer-approved venue.
- **Review intensity:** Standard for the checklist; Strict for the migration the checklist authorizes.
- **Per-domain review pattern:** Status and reporting outputs (when shared with manager / IT / security).

## Use rules

- One checklist per artifact migration. Bulk migrations are not allowed.
- Every question is answered explicitly: yes / no / unclear / not applicable. Blank answers are not acceptable.
- A "no" or "unclear" on any gating question is a stop. Resume after the underlying issue is resolved and a new checklist instance is filled.
- The completed checklist is filed in the employer audit venue, not in ATLAS, once a real migration occurs. Personal-preparation runs of the checklist (against synthetic content) can be kept in personal notes.
- Tom does not sign off the checklist alone. The named accountable employer reviewer signs off the gates that fall within their responsibility.

## Checklist

```text
Artifact migration readiness checklist
Artifact ID / Title: [Source artifact in ATLAS (path) and migrated artifact's intended location]
Tom prep date: [YYYY-MM-DD]
Accountable employer reviewer: [Role and name]
Reviewer sign-off date: [YYYY-MM-DD]

Gate 1 — Approval
- [ ] Tool is on the employer-approved list for the relevant data category. (yes / no / unclear)
- [ ] Data category routing is documented and consistent with `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. (yes / no / unclear)
- [ ] Six-step approval pattern from `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` has been walked end-to-end. (yes / no)
- [ ] Approval is documented in the employer audit venue. (yes / no — name the record)
- [ ] If any answer above is "no" or "unclear," STOP and resolve before proceeding.

Gate 2 — Owner and review
- [ ] Named accountable employer reviewer has accepted the role for this migrated artifact. (yes / no)
- [ ] Reviewer understands the review intensity (Standard or Strict) and the per-domain review pattern from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`. (yes / no)
- [ ] Sign-off and audit-record location are agreed before any real-data use. (yes / no — name the location)

Gate 3 — Scope and data
- [ ] Migration scope is named explicitly (one artifact; one tool; one data category). (yes / no)
- [ ] Real-data pilot is not the first run; synthetic / sanitized input precedes any real use. (yes / no)
- [ ] Data export from ATLAS (if any) is reviewed for sensitivity; no personal-preparation content carries restricted material into the employer venue. (yes / no — name what was reviewed)
- [ ] Filenames, metadata, and screenshots have been checked for inadvertent disclosure. (yes / no)

Gate 4 — Pilot
- [ ] Pre-flight checklist from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` ran clean for the pilot. (yes / no)
- [ ] Pilot output was reviewed at the agreed intensity. (yes / no)
- [ ] Post-flight checklist ran clean. (yes / no)
- [ ] Findings (if any) are captured in the employer audit venue. (yes / no — name the record)

Gate 5 — Steady-state readiness
- [ ] Owner role for the migrated artifact is named and the role expectations are documented. (yes / no)
- [ ] Review cadence (e.g., quarterly) and the role responsible for the next review are documented. (yes / no — name the cadence and role)
- [ ] Audit-trail expectations for the artifact's outputs are documented (where logs, drafts, and final approvals live). (yes / no — name the locations)
- [ ] The personal-preparation version in ATLAS is marked as the reference copy, not the source of truth. (yes / no)

Gate 6 — Rollback
- [ ] `11_MIGRATION/MIGRATION_ROLLBACK_NOTE.md` has been filled in for this artifact. (yes / no — name the rollback note's location)
- [ ] Rollback owner is named and has confirmed the rollback plan. (yes / no)
- [ ] Reversibility was tested at the pilot stage (not just described). (yes / no)
- [ ] Trigger conditions that would require rollback are explicit. (yes / no — name the conditions)

Gate 7 — Final go / no-go
- [ ] All gates above have at least one "yes" answer per gating question; no "no" or "unclear" remains open. (yes / no)
- [ ] Accountable reviewer signs go-live. (yes / no — name and date)
- [ ] Tom records the migration decision in the appropriate ATLAS decision log if the decision is durable, with reference to the audit record in the employer venue. (yes / no — reference D-NNNN if applicable)
```

## Failure modes

- A "no" or "unclear" gets a hand-wave ("we'll come back to it"). Treat as a hard stop.
- The checklist is filled in by Tom alone without the accountable employer reviewer's involvement. Restart with the reviewer engaged.
- Gates skipped because the migration "feels low risk." Risk perception is not a gate; the discipline is the gate.
- Bulk migration ("let's move everything at once"). One artifact at a time.
- Rollback step skipped because "we won't need it." A migration without a tested rollback is not a migration.

## Cross-references

- Parent file: `11_MIGRATION/EMPLOYER_MIGRATION_PLAN.md`.
- Sibling file: `11_MIGRATION/MIGRATION_ROLLBACK_NOTE.md`.
- Governance bundle: `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0060.
- Decision log: D-0058..D-0060 (Phase 11 set).
