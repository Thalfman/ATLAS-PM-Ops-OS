# SYNTHETIC_DISCREPANCY_TRIAGE_DEMO.md

**SYNTHETIC DEMO. FICTIONAL ISSUES AND DISCREPANCIES. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0051
- **Phase:** 7 - Synthetic Demo Pack
- **Paired workflow card:** `04_WORKFLOWS/W-08-issue-and-discrepancy-triage.md`
- **Paired prompt card:** `05_PROMPTS/P-08-issue-and-discrepancy-triage.md`
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`
- **Pack index:** `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Governance envelope

- **Data category:** Synthetic.
- **Tool environment:** ATLAS-local Markdown; Personal AI tool acceptable for the AI-step exercise.
- **Review intensity:** Light for personal practice.
- **Per-domain review pattern:** Risk and issue triage outputs (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`).

## Demo purpose

Walk an issue / discrepancy triage end-to-end: a fictional inbox of mixed-shape issue notes on Project Northstar Demo, an AI-drafting step using P-08 that produces a structured triage table without assigning severity or owner, and a human-review pass where Tom does the assignments.

## Step 1 - Synthetic issue inbox

Six fictional issue notes captured during week 3 from a mix of meetings, walkup conversations, and ATLAS observations. Each note is intentionally rough.

```text
1. "Action tracker shows three actions with the same description but different owners — pretty sure these are duplicates from when the tool was being tested last week. Need to consolidate before the week 3 readout."
2. "Reporting Coordinator flagged that the week 2 status pack had two different counts for open actions (6 in the table, 5 in the narrative). Wasn't sure which was right."
3. "Workstream C Lead can't access the decision log section in the meeting template — they say the column doesn't render in their view."
4. "Risk R-001 mitigation 'confirm owners at meeting close' wasn't applied at the 2026-05-15 meeting. Two new actions still got opened without a date."
5. "Lessons learned draft references a 'pilot retrospective' that hasn't happened yet. Either the draft is premature or the retrospective is missing from the schedule."
6. "Sponsor asked whether the M-05 milestone (Reporting pack adopted) is still 2026-05-29 or has slipped. We don't have a current answer in the pack."
```

## Step 2 - AI step (P-08 invocation pattern)

Tom runs `P-00-safety-precheck.md`: Synthetic, Personal AI tool, Tom as reviewer, paired W-08. Clear.

Tom sends the inbox through P-08 with placeholders filled. P-08 forbids AI from assigning severity or owner; AI proposes investigation questions and structures the rows.

## Step 3 - AI triage table (before review)

| # | One-line description | Severity (S1-S4) | Affected scope | Owner | Next step | Target date | Status | Notes |
|---|---|---|---|---|---|---|---|---|
| 1 | Action tracker shows likely duplicates with different owners. | (Tom to assign) | Workstream B; action tracker | (Tom to assign) | Reconcile duplicates by comparing source meeting notes; confirm owners before consolidation. | 2026-05-24 (pre-readout) | Open | AI flags this as a hygiene reconciliation, not a stop-work item. |
| 2 | Week 2 status pack has inconsistent open-action counts (6 vs 5). | (Tom to assign) | Workstream A; reporting pack | (Tom to assign) | Recompute open-action count from the tracker as of 2026-05-15 cutoff; correct the pack copy or the table, whichever drifted. | 2026-05-24 | Open | Investigation candidate — AI suggests checking whether one count counted A-001 as still open before closure. |
| 3 | Workstream C Lead cannot access decision-log column in meeting template. | (Tom to assign) | Workstream C; template tooling | (Tom to assign) | Investigation candidate. AI suggests questions: which view is Workstream C Lead using; was the column added to the template after the lead's local copy was made; does the rendering issue reproduce for other leads. | (depends on investigation) | Open | Could be S2 (degrades quality) or S3 (inconveniences) depending on impact; Tom decides. |
| 4 | R-001 mitigation not applied at 2026-05-15 meeting; two actions opened without dates. | (Tom to assign) | Workstream B; risk register | (Tom to assign) | Convert R-001 mitigation into a meeting-close requirement and add to the meeting template; close the date gaps on the two open actions. | 2026-05-22 | In progress | Cross-references action A-105. |
| 5 | Lessons learned draft references a pilot retrospective not on the schedule. | (Tom to assign) | Workstream A; Workstream B; schedule | (Tom to assign) | Confirm whether the retrospective is planned (schedule update needed) or whether the draft language is premature (draft edit needed). | 2026-05-24 | Open | Investigation candidate — AI proposes the two-branch question rather than asserting which is right. |
| 6 | Sponsor question on M-05 status has no current answer in the pack. | (Tom to assign) | Workstream A; reporting pack | (Tom to assign) | Confirm current M-05 finish date from the schedule (current finish: 2026-06-02 per the schedule variance demo), update the pack, and decide whether to flag the +4 day slip as a decision needed. | 2026-05-24 (pre-readout) | Open | Cross-references the schedule variance demo. |

Severity definitions (carried from W-08 §7):

- S1: stops work.
- S2: degrades quality or schedule.
- S3: inconveniences.
- S4: informational.

Investigation candidates (rows 2, 3, 5): the next step is "investigate," not "fix." AI lists questions to ask; AI does not draw the conclusion.

Open ownership (all six rows): no owner assigned. Tom does the assignments based on workstream alignment and capacity.

## Step 4 - Human review (Risk and issue triage outputs pattern)

Per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Risk and issue triage outputs":

- **Every entry has an owner?** Not yet — AI left assignments to Tom. Tom assigns: row 1 → Workstream B Lead; row 2 → Reporting Coordinator; row 3 → Workstream C Lead (with PM/Ops support); row 4 → Team Lead; row 5 → Workstream A Lead; row 6 → PM/Ops.
- **Categorization matches judgment, not inference?** Tom assigns severity: row 1 S3 (hygiene), row 2 S2 (data quality impacts trust), row 3 S3 (tooling annoyance), row 4 S2 (governance gap), row 5 S2 (artifact inconsistency), row 6 S2 (sponsor visibility).
- **Mitigation or next step is actionable?** Yes for rows 1, 2, 4, 6; rows 3 and 5 are correctly flagged as investigation candidates.

## Step 5 - Final triage table (after review)

| # | Description | Severity | Affected scope | Owner | Next step | Target date | Status |
|---|---|---|---|---|---|---|---|
| 1 | Action tracker duplicates with different owners. | S3 | Workstream B; action tracker | Workstream B Lead | Reconcile duplicates by comparing source meeting notes; confirm owners before consolidation. | 2026-05-24 | Open |
| 2 | Week 2 status pack has inconsistent open-action counts. | S2 | Workstream A; reporting pack | Reporting Coordinator | Recompute open-action count from the tracker; correct the pack or the table. | 2026-05-24 | Open |
| 3 | Workstream C Lead cannot access decision-log column. | S3 | Workstream C; tooling | Workstream C Lead (PM/Ops supports) | Investigate which view, whether reproduces, whether template version mismatch. | 2026-05-26 | Open |
| 4 | R-001 mitigation not applied; two actions opened without dates. | S2 | Workstream B; risk register | Team Lead | Make the meeting-close requirement explicit in the template; close the two date gaps. | 2026-05-22 | In progress |
| 5 | Lessons learned draft references a pilot retrospective not on the schedule. | S2 | Workstreams A and B; schedule | Workstream A Lead | Confirm whether retrospective is planned (schedule update) or draft language is premature (edit draft). | 2026-05-24 | Open |
| 6 | Sponsor question on M-05 status has no current answer. | S2 | Workstream A; reporting pack | PM/Ops | Confirm current M-05 finish (2026-06-02 per schedule demo); update pack; flag +4 day slip as decision needed. | 2026-05-24 | Open |

```text
Reviewer sign-off: Tom (Light intensity, synthetic input), 2026-05-23.
Owner assignments confirmed via informal walkthrough with attendees prior to the week 3 readout.
```

## Demo value

The AI structures the inbox into a triage table and surfaces investigation candidates without overstepping. Severity, owner, and the final next-step language are human decisions — AI proposes, Tom assigns. The pattern transfers to real issue triage only after the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` is walked for that data and tool environment (W-08 §14).

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-08-issue-and-discrepancy-triage.md`.
- Paired prompt card: `05_PROMPTS/P-08-issue-and-discrepancy-triage.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Cross-demo reference: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md` (row 6 references the M-05 schedule slip).
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0051.
