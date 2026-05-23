# SYNTHETIC_STATUS_PACK_DEMO.md

**SYNTHETIC DEMO. FICTIONAL PROJECT, FICTIONAL DATA. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0007
- **Phase:** 7 - Synthetic Demo Pack
- **Paired workflow card:** `04_WORKFLOWS/W-01-weekly-status-report.md` (drafting) and `04_WORKFLOWS/W-12-executive-brief-generation.md` (executive narrative)
- **Paired prompt card:** `05_PROMPTS/P-01-weekly-status-drafting.md` (status) and `05_PROMPTS/P-12-executive-brief-drafting.md` (executive)
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`
- **Pack index:** `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Governance envelope

- **Data category:** Synthetic.
- **Tool environment:** ATLAS-local Markdown; Personal AI tool acceptable for the AI-step exercise.
- **Review intensity:** Light for personal practice.
- **Per-domain review pattern:** Status and reporting outputs (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`).

## Demo purpose

Walk a weekly status pack end-to-end on Project Northstar Demo: synthetic inputs (accomplishments, schedule movement, risks, issues, actions), an AI-drafting step using P-01 / P-12 that produces a weekly status draft and an executive summary, and a human-review pass following the "Status and reporting outputs" pattern. This is the seeded demo from earlier sessions, hardened in Phase 7 with the paired W / P / governance envelope and the shared-scenario structure.

## Step 1 - Synthetic inputs

Drawn from Project Northstar Demo week 2, 2026-05-11 through 2026-05-15.

### Accomplishments

- Drafted a standard weekly status format.
- Created a fictional action tracker with owners, due dates, and aging indicators.
- Identified recurring status gaps: unclear owners, missing due dates, and weak decision logs.
- Completed a first-pass risk cleanup using condition-consequence wording.

### Schedule movement

| Milestone | Baseline date | Current date | Variance | Notes |
|---|---:|---:|---:|---|
| Draft reporting template | 2026-05-13 | 2026-05-13 | 0 days | Complete. |
| Action tracker pilot | 2026-05-15 | 2026-05-17 | +2 days | Delayed by owner availability. |
| Risk review workshop | 2026-05-20 | 2026-05-20 | 0 days | On track. |
| Lessons learned draft | 2026-05-22 | 2026-05-24 | +2 days | Dependent on pilot feedback. |

### Synthetic risks

| Risk ID | Risk statement | Trigger | Mitigation | Owner | Status |
|---|---|---|---|---|---|
| R-001 | If action owners are not confirmed during meetings, follow-up may be delayed and status quality may decline. | More than 20% of actions have TBD owners. | Require owner/date confirmation before meeting close. | PM/Ops | Open |
| R-002 | If the status format is too complex, adoption may be inconsistent. | Users skip sections or create parallel formats. | Keep format to one page and review after two cycles. | PM/Ops | Open |

### Synthetic issues

| Issue ID | Issue | Impact | Next action | Owner | Due |
|---|---|---|---|---|---|
| I-001 | Three actions from the prior meeting had no due date. | Aging cannot be measured. | Confirm due dates with owners. | PM/Ops | 2026-05-16 |
| I-002 | Decision notes are captured inconsistently. | Rework and misalignment risk. | Add decision log section to meeting template. | PM/Ops | 2026-05-17 |

### Synthetic action items

| Action ID | Action | Owner | Due date | Status | Aging |
|---|---|---|---|---|---:|
| A-001 | Finalize weekly status template. | PM/Ops | 2026-05-13 | Complete | 0 |
| A-002 | Confirm owners for open actions. | PM/Ops | 2026-05-16 | Open | 1 |
| A-003 | Draft decision log format. | PM/Ops | 2026-05-17 | Open | 0 |
| A-004 | Review risk wording with team lead. | Team Lead | 2026-05-20 | Not started | 0 |

## Step 2 - AI step (P-01 for status, P-12 for executive)

Tom runs `P-00-safety-precheck.md`: Synthetic, Personal AI tool, Tom as reviewer, paired W-01 / W-12. Clear.

Tom sends the synthetic inputs through P-01 to draft the weekly status, then through P-12 to compress to an executive summary.

## Step 3 - AI drafts (before review)

### Weekly status draft (P-01 output)

```text
Project: Synthetic Project Northstar Demo
Reporting period: 2026-05-11 to 2026-05-15
Status color: Yellow (one milestone +2 days; recovery path identified)

Bottom line
Project Northstar Demo completed the weekly status template on schedule and began the action tracker pilot two days behind plan due to owner availability. Operating-rhythm discipline (owner confirmation, decision capture) is the most consistent risk theme this week.

Accomplishments
- Drafted and approved the standard weekly status format.
- Stood up the action tracker prototype with owners, due dates, and aging indicators.
- Completed a first-pass risk cleanup using condition-consequence wording (R-001, R-002).
- Identified three recurring status gaps: unclear owners, missing due dates, weak decision logs.

Schedule
- M-01 Reporting template approved (2026-05-13, on time).
- M-02 Action tracker pilot started 2026-05-17 (baseline 2026-05-15, +2 days; cause: owner availability).
- M-03 Risk review workshop scheduled 2026-05-20 (on track).
- M-04 Lessons learned draft moves to 2026-05-24 (+2 days, dependent on pilot feedback).

Open risks (top two)
- R-001 (open, PM/Ops): owner confirmation not yet a meeting-close requirement.
- R-002 (open, PM/Ops): template adoption to be reviewed after two cycles.

Open issues (top two)
- I-001 (PM/Ops, due 2026-05-16): three actions from the prior meeting had no due date.
- I-002 (PM/Ops, due 2026-05-17): decision capture inconsistent across meetings.

Open actions
- A-002, A-003 PM/Ops-owned; A-004 Team Lead.

Decisions or inputs needed
- None this week; the M-02 +2 day finish is within tolerance and the recovery path is visible.
```

### Executive summary draft (P-12 output, compressed to ~5 sentences)

```text
Project Northstar Demo is yellow this week. The weekly status template was completed on schedule and the action tracker pilot moved from 2026-05-15 to 2026-05-17 because of owner availability for confirming assignments. The operating-rhythm discipline theme (owner confirmation, decision capture) is the consistent risk pattern; mitigation is to make owner/date confirmation a meeting-close requirement. No decision is requested this week. The recommended next step is to confirm owners and due dates for all open actions and to use the 2026-05-20 risk-review workshop to validate whether the simplified reporting format is practical for recurring use.
```

## Step 4 - Human review (Status and reporting outputs pattern)

Per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Status and reporting outputs":

- **Every claim has a source the reviewer can point to?** Each accomplishment, schedule entry, risk, issue, and action in both drafts traces to the synthetic inputs above. Pass.
- **Language implies certainty the source supports?** "Operating-rhythm discipline is the most consistent risk theme this week" is supported by R-001, I-001, I-002 all touching owner/decision discipline. Pass.
- **Forward-looking statements marked?** "Lessons learned draft moves to 2026-05-24" is the only forward-looking item; it is stated as a current schedule date, not a commitment. The executive summary's "recommended next step" is correctly framed as a recommendation, not a decision. Pass.
- **Risks stated, not hidden?** R-001 and R-002 named with owners and status. Pass.

Tom would make one edit before sharing: tighten the bottom-line color rationale from one sentence to a clear pair: "Yellow because M-02 +2 days; recovery path visible; no decision requested."

## Step 5 - Final pack (after review)

The drafts above with the one-line bottom-line tightening and a sign-off block:

```text
Drafted by Tom on 2026-05-23 (synthetic practice).
Reviewed by Tom on 2026-05-23 (Light intensity, synthetic input).
Adjustments after review: bottom-line color rationale tightened to "Yellow because M-02 +2 days; recovery path visible; no decision requested."
```

## Demo value

This demo illustrates a safe, practical AI-enabled status pack workflow:

1. Structure raw PM/Ops inputs.
2. Flag missing owner / date / decision details.
3. Draft a concise executive narrative.
4. Draft a variance explanation (handled in `SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md`).
5. Preserve human review and approval.

Migration to real status data requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` and routing to an Employer-approved AI tool inside the approved scope (W-01 §14, W-12 §14).

## Cross-references

- Paired workflow cards: `04_WORKFLOWS/W-01-weekly-status-report.md`, `04_WORKFLOWS/W-12-executive-brief-generation.md`.
- Paired prompt cards: `05_PROMPTS/P-01-weekly-status-drafting.md`, `05_PROMPTS/P-12-executive-brief-drafting.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Cross-demo references: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md` (variance narrative drilled down); `08_SYNTHETIC_DEMOS/SYNTHETIC_ACTION_TRACKER_DEMO.md` (action discipline); `08_SYNTHETIC_DEMOS/SYNTHETIC_RISK_REGISTER_CLEANUP_DEMO.md` (R-001 / R-002 cleanup); `08_SYNTHETIC_DEMOS/SYNTHETIC_DISCREPANCY_TRIAGE_DEMO.md` (issue triage).
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0007.
