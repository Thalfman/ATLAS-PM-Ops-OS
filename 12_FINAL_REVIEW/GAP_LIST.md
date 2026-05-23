# GAP_LIST.md

## Artifact identity

- **Backlog ID:** A-0063
- **Phase:** 12 - Final Operating System Review
- **Parent file:** `12_FINAL_REVIEW/FINAL_OPERATING_SYSTEM_REVIEW.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A short, honest list of what is missing, weak, or stale in ATLAS at the end of Phase 12. The gap list is the input to the maintenance plan; it does not block "all phases complete" but it captures the items a future session would pick up.

## Governance envelope

- **Data category:** Tom-personal.
- **Tool environment:** ATLAS-local Markdown.
- **Review intensity:** Standard (this list shapes the maintenance plan and the next operating cycle).
- **Per-domain review pattern:** Status and reporting outputs.

## Open backlog rows (carried forward)

These rows remain `Not started` at the end of Phase 12. They are housekeeping, not blockers.

| Row | Title | Notes |
|---|---|---|
| A-0038 | Process Gap Note Workflow | W-16 reserved. Pairs naturally with `LISTENING_PLAN.md`. Build as `04_WORKFLOWS/W-16-process-gap-note.md` in a follow-up chore session. |
| A-0029 | Local skill files refresh | Phase 4 / 5 / 6 / 7 / 8 / 9 / 10 patterns are now stable. The three `skills/*/SKILL.md` files (`atlas-bootstrap`, `atlas-handoff`, `atlas-safety`) can be re-checked against current schemas in a chore session. |

## Indexing and reconciliation gaps

| Gap | Where | Suggested action |
|---|---|---|
| Phase 9 EVM / accounting demos are not listed in the Phase 7 demo pack index. | `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md` "Pack index" table. | Add `SYNTHETIC_EVM_WORKBOOK.md` and `SYNTHETIC_ACCOUNTING_RECONCILIATION_DEMO.md` rows. |
| The Phase 7 demo pack rules list "no real-data blending" but the synthetic EVM / accounting demos are richer than the original pack rules anticipated. | `SYNTHETIC_DEMO_PACK.md` rules vs new content. | Confirm the existing rules still apply unchanged (they do). No action required unless review surfaces a tension. |
| `SCHEDULE_HEALTH_REVIEW_TEMPLATE.md` references a "Synthetic schedule health review" demo that was not built in Phase 8. | `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md` cross-references. | Optional Phase 12+ housekeeping: build a worked example demo against `SYNTHETIC_SCHEDULE_WORKBOOK.md`. |
| The Phase 9 W-17 card mentions A-0037 cross-tool mismatch as a related workflow, but A-0037 is a Phase 4 backlog row, not a workflow card. | `04_WORKFLOWS/W-17-accounting-discrepancy-triage.md` §15. | Minor: clarify the reference is to W-13 (the cross-tool mismatch workflow card) and A-0037 (the backlog row). |

## Coverage gaps

| Gap | Why it is open | Suggested action |
|---|---|---|
| No "dashboards" deliverable. | ATLAS is Markdown-first by design; dashboards are post-clearance employer-environment scope. | Keep out of scope until employer migration phase (Phase 11+ activity, after approvals). |
| No worked SOP example produced in Phase 10. | The `SOP_TEMPLATE.md` is fillable; a worked example was not built to avoid scope creep. | Optional: produce a fictional SOP for the Phase 7 / 8 / 9 reporting cycle as a follow-up. |
| No worked lessons-learned record produced in Phase 10. | Same as above. | Optional: produce a fictional lessons-learned record covering the Phase 7 scenario. |
| No knowledge-base instantiation example. | `KNOWLEDGE_BASE_PATTERN.md` cross-references ATLAS's own indexes as instantiations, but a deployed example (in Workspace / SharePoint / wiki) was not built. | Out of scope; instantiation is post-approval employer work. |
| The `EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md` covers Sections A-J in the original Phase 3 build but only Section A is shown in the question summary table inside `ONBOARDING_QUESTION_SET.md`. | Onboarding question set is summary; the full bank is in the governance file. | No action; the cross-reference is sufficient. |

## Posture gaps

| Gap | Why it is open | Suggested action |
|---|---|---|
| Phase 11 migration plan does not name a specific tool. | By design (D-0059). | No action; this is the binding rule. If employer policy becomes known, log a new decision and update the plan. |
| Phase 6 kit does not assume any specific Workspace / SharePoint / wiki tooling. | By design (Gemini-first, platform-agnostic). | No action; tool assumptions are post-onboarding. |
| No retrospective process on ATLAS itself. | The decision log captures durable choices; a retrospective process is not currently part of the operating rhythm. | Considered in `OPERATING_RHYTHM.md` — a quarterly retro is the proposal. |

## Things deliberately not added

These are not gaps; they are decisions to not build. Listed here so a future reader does not mistake the absence for an oversight.

- Apps, package dependencies, APIs, databases, deployment files, frontend/backend code, code scaffolds (D-0001). The one CI exception (`.github/workflows/codex-review-loop.yml`) is authorized per D-0022.
- Real employer tool wrappers, integrations, or scripts. ATLAS is Markdown-first.
- Real-data examples anywhere. The safety boundary is binding.
- A unified "search across ATLAS" tool. Grep is sufficient.
- Auto-generated documentation. The library / pack / kit indexes are hand-maintained, which is the right tradeoff for a personal-preparation operating system at this size.

## How to use this list

- The maintenance plan (`MAINTENANCE_PLAN.md`) names a cadence for revisiting this list.
- Items moving from "open" to "closed" get a logged decision in `10_DECISION_LOG/DECISION_LOG.md` if the decision is durable.
- New gaps surfaced after Phase 12 are appended here; the list is append-only in the sense that items move between sections, but the file remains the single inventory of open work.

## Cross-references

- Parent file: `12_FINAL_REVIEW/FINAL_OPERATING_SYSTEM_REVIEW.md`.
- Sibling files: `12_FINAL_REVIEW/OPERATING_RHYTHM.md`, `12_FINAL_REVIEW/MAINTENANCE_PLAN.md`.
- Source-of-truth: `03_BACKLOG/ARTIFACT_BACKLOG.md`, `10_DECISION_LOG/DECISION_LOG.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0063.
