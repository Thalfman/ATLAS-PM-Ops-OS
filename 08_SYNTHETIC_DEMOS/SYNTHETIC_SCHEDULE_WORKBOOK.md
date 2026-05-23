# SYNTHETIC_SCHEDULE_WORKBOOK.md

**SYNTHETIC WORKBOOK. FICTIONAL SCHEDULE. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0053
- **Phase:** 8 - Microsoft Project and Schedule Integrity Track
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`
- **Pack index:** `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`
- **Paired templates:** `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`, `07_TEMPLATES/SCHEDULE_VARIANCE_NARRATIVE_TEMPLATE.md`
- **Paired Phase 7 demo:** `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md` (uses a compact subset of this workbook)
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A richer fictional schedule for Project Northstar Demo with multiple workstreams, dependencies, critical-path identification, baseline vs current dates, slack, and constraints. The workbook is Markdown / table-based and never a real `.mpp` file. It exists so the Phase 8 schedule-health checklist and variance template have a realistic substrate, and so Phase 7's compact schedule snapshot has a longer-form sibling for more substantial walkthroughs.

The workbook obeys the Phase 7 pack rules: bold synthetic label, no real names, no real numbers, AI never decides or commits dates, no claim of deployment-readiness.

## Governance envelope

- **Data category:** Synthetic.
- **Tool environment:** ATLAS-local Markdown; Personal AI tool acceptable for any AI-assisted exercise against this workbook because the input is Synthetic.
- **Review intensity:** Light for personal practice.
- **Per-domain review pattern:** Schedule outputs (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`).

Full citation pattern inherited from `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.

## Scope and shape

- **Project:** Synthetic Project Northstar Demo.
- **Horizon:** 6 weeks, 2026-05-04 through 2026-06-12.
- **Workstreams:** A (Reporting), B (Action tracking), C (Risk and decision capture). Names match the shared scenario.
- **Tasks:** 24, distributed across the three workstreams plus a small Management workstream.
- **Milestones:** 6 (M-01..M-06 per the shared scenario).
- **Snapshot date / data date:** 2026-05-22 (Friday of week 3). Variance values below are calculated at this snapshot.

## Workbook

Columns: Task ID, Workstream, Task, Predecessors, Baseline start, Baseline finish, Current start, Current finish, % Complete, Total slack (working days), Critical path?, Constraint, Notes.

| Task ID | WS | Task | Preds | Baseline start | Baseline finish | Current start | Current finish | % | Slack | CP? | Constraint | Notes |
|---|---|---|---|---:|---:|---:|---:|---:|---:|---|---|---|
| NS-M-01 | Mgmt | Project kickoff (milestone) | — | 2026-05-04 | 2026-05-04 | 2026-05-04 | 2026-05-04 | 100 | 0 | Yes | None | M-00 implicit. |
| NS-A-01 | A | Draft weekly status template | NS-M-01 | 2026-05-04 | 2026-05-08 | 2026-05-04 | 2026-05-08 | 100 | 0 | Yes | None | Complete. |
| NS-A-02 | A | Stakeholder review of template | NS-A-01 | 2026-05-11 | 2026-05-13 | 2026-05-11 | 2026-05-13 | 100 | 0 | Yes | None | Complete. |
| NS-M-02 | Mgmt | Weekly status template approved (milestone) | NS-A-02 | 2026-05-13 | 2026-05-13 | 2026-05-13 | 2026-05-13 | 100 | 0 | Yes | None | Met. |
| NS-B-01 | B | Build action tracker prototype | NS-M-02 | 2026-05-11 | 2026-05-15 | 2026-05-12 | 2026-05-17 | 100 | 0 | Yes | None | +2 day finish; owner-availability cause per Phase 7 variance demo. |
| NS-B-02 | B | Confirm action owners across team | NS-B-01 | 2026-05-15 | 2026-05-15 | 2026-05-17 | 2026-05-19 | 80 | -1 | No | None | +4 day finish; depends on NS-B-01 finish. Slack negative — recovery posture needed. |
| NS-M-03 | Mgmt | Action tracker pilot starts (milestone) | NS-B-02 | 2026-05-15 | 2026-05-15 | 2026-05-19 | 2026-05-19 | 100 | -1 | Yes | None | +4 days vs baseline; pilot started against re-confirmed owners. |
| NS-C-01 | C | Schedule risk-review workshop | NS-A-02 | 2026-05-18 | 2026-05-20 | 2026-05-18 | 2026-05-20 | 100 | 2 | No | None | On track. |
| NS-M-04 | Mgmt | Risk-review workshop held (milestone) | NS-C-01 | 2026-05-20 | 2026-05-20 | 2026-05-20 | 2026-05-20 | 100 | 2 | No | None | Met. |
| NS-C-02 | C | Lessons learned first draft | NS-B-01, NS-M-04 | 2026-05-20 | 2026-05-22 | 2026-05-22 | 2026-05-24 | 50 | 0 | No | None | +2 day finish; depends on pilot feedback. |
| NS-A-03 | A | Reporting pack pilot run | NS-B-02, NS-M-02 | 2026-05-25 | 2026-05-29 | 2026-05-27 | 2026-06-02 | 25 | -4 | Yes | None | +4 day finish driven by upstream slip; recovery posture not yet captured. |
| NS-M-05 | Mgmt | Reporting pack adopted (milestone) | NS-A-03 | 2026-05-29 | 2026-05-29 | 2026-06-02 | 2026-06-02 | 0 | -4 | Yes | None | +4 days vs baseline; sponsor visibility per Phase 7 triage demo row 6. |
| NS-A-04 | A | Reporting pack leadership readout | NS-M-05 | 2026-06-01 | 2026-06-01 | 2026-06-03 | 2026-06-03 | 0 | -2 | Yes | Start No Earlier Than 2026-06-01 | Constraint left from original plan; reviewer to confirm whether still appropriate. |
| NS-C-03 | C | Decision-log adoption in meeting template | NS-A-02 | 2026-05-18 | 2026-05-22 | 2026-05-18 | 2026-05-22 | 90 | 1 | No | None | On track. |
| NS-B-03 | B | Action aging cadence | NS-M-03 | 2026-05-20 | 2026-05-25 | 2026-05-22 | 2026-05-27 | 60 | 0 | No | None | +2 day finish following NS-M-03 slip. |
| NS-B-04 | B | Owner-confirmation meeting-close requirement | NS-B-02 | 2026-05-19 | 2026-05-22 | 2026-05-21 | 2026-05-22 | 100 | 0 | No | None | Adopted via R-001 mitigation; cross-references Phase 7 risk demo. |
| NS-C-04 | C | Pilot retrospective | NS-A-03 | (not in baseline) | (not in baseline) | (TBD) | (TBD) | 0 | (n/a) | No | None | Discrepancy flagged by Phase 7 triage demo row 5 — retrospective is in lessons-learned draft but not on the schedule. Reviewer to add or remove. |
| NS-A-05 | A | Sustainment review preparation | NS-M-05 | 2026-06-03 | 2026-06-08 | 2026-06-04 | 2026-06-09 | 0 | -1 | Yes | None | Carries +1 day from M-05 slip. |
| NS-M-06 | Mgmt | Sustainment review with sponsor (milestone) | NS-A-05 | 2026-06-12 | 2026-06-12 | 2026-06-12 | 2026-06-12 | 0 | 3 | No | Must Finish On 2026-06-12 | Hard constraint from sponsor; absorbs some upstream slip. |
| NS-A-06 | A | Reporting pack post-readout edits | NS-A-04 | 2026-06-02 | 2026-06-04 | 2026-06-04 | 2026-06-08 | 0 | -2 | Yes | None | +4 days finish; tied to upstream chain. |
| NS-C-05 | C | Decision-log audit | NS-C-03 | 2026-05-25 | 2026-05-28 | 2026-05-25 | 2026-05-28 | 30 | 4 | No | None | On track. |
| NS-B-05 | B | Tracker hygiene pass | NS-B-03 | 2026-05-27 | 2026-05-29 | 2026-05-29 | 2026-06-01 | 0 | 1 | No | None | +2 day finish following NS-B-03 slip. |
| NS-A-07 | A | Lessons learned incorporation | NS-C-02 | 2026-05-25 | 2026-05-29 | 2026-05-27 | 2026-06-01 | 0 | 2 | No | None | +3 day finish following NS-C-02 slip. |
| NS-A-08 | A | Final pack archive | NS-A-06, NS-M-06 | 2026-06-08 | 2026-06-12 | 2026-06-10 | 2026-06-12 | 0 | 0 | Yes | None | Constrained by NS-M-06. |

## Critical path

At 2026-05-22 snapshot, the critical path (longest chain with zero or negative total slack) is:

```text
NS-M-01 -> NS-A-01 -> NS-A-02 -> NS-M-02 -> NS-B-01 -> NS-M-03 -> NS-A-03 -> NS-M-05 -> NS-A-04 -> NS-A-06 -> NS-A-08
```

Current total slip on this path is +4 days against baseline, fully absorbed by the Must Finish On 2026-06-12 constraint on NS-M-06. NS-B-02 carries -1 day slack and is not on the longest path but is a near-critical predecessor of NS-M-03; NS-A-03's -4 day slack is the deepest current slip.

## Findings the schedule reveals (illustrative; the health template runs through these)

- **Baseline integrity:** Baseline columns present and consistent. No re-baseline this period.
- **Milestone discipline:** All six milestones present and dated; M-01..M-04 met; M-05 +4 days; M-06 hard constraint absorbs the chain.
- **Orphan tasks:** None — every task has at least one predecessor and at least one successor.
- **Constraints:** Two constraints (NS-A-04 SNET 2026-06-01, NS-M-06 MFO 2026-06-12). Both flagged for review; NS-A-04 may be a legacy constraint.
- **Lags / leads:** None.
- **Negative slack:** NS-B-02 (-1), NS-A-03 (-4), NS-M-05 (-4), NS-A-04 (-2), NS-A-05 (-1), NS-A-06 (-2). All trace to the upstream NS-B-01 slip.
- **Discrepancy:** NS-C-04 (pilot retrospective) is referenced in the lessons-learned draft but not in the baseline; reviewer to add (with predecessor NS-A-03) or remove the lessons-learned reference. Cross-references Phase 7 discrepancy triage demo row 5.
- **Owner clarity:** Workstream-level ownership clear. Per-task owner not shown in this workbook (kept to schedule columns); the action tracker carries owner detail.

## How to use this workbook

1. With `SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`: run the A..L checklist against the table above. Each section's "yes / no / not visible" answers populate the template's output shape.
2. With `SCHEDULE_VARIANCE_NARRATIVE_TEMPLATE.md` and `P-05`: extract the moved activities and feed them into the variance template. The Phase 7 schedule variance demo already does this for a compact subset; this workbook supports a fuller version.
3. As a synthetic-demo backdrop in conversations: walk through the critical path, the upstream cause (NS-B-01), the milestone absorption (NS-M-06), and the schedule's own indicators of recovery posture (or absence of them).

## Cross-references

- Paired templates: `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`, `07_TEMPLATES/SCHEDULE_VARIANCE_NARRATIVE_TEMPLATE.md`.
- Paired Phase 4 / 5 cards: `04_WORKFLOWS/W-04-schedule-health-review.md`, `04_WORKFLOWS/W-05-schedule-variance-narrative.md`, `05_PROMPTS/P-05-schedule-variance-narrative.md`.
- Phase 7 demos that draw from this scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md`, `08_SYNTHETIC_DEMOS/SYNTHETIC_DISCREPANCY_TRIAGE_DEMO.md` (row 5, NS-C-04 reference), `08_SYNTHETIC_DEMOS/SYNTHETIC_RISK_REGISTER_CLEANUP_DEMO.md` (NS-B-04 implements R-001 mitigation).
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0053.
