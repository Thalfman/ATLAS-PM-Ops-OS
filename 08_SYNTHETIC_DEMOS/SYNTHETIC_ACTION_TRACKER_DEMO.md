# SYNTHETIC_ACTION_TRACKER_DEMO.md

**SYNTHETIC DEMO. FICTIONAL MEETING NOTES AND ACTION ITEMS. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0024
- **Phase:** 7 - Synthetic Demo Pack
- **Paired workflow cards:** `04_WORKFLOWS/W-02-meeting-notes-to-actions.md` (extraction), `04_WORKFLOWS/W-03-action-item-aging.md` (aging)
- **Paired prompt cards:** `05_PROMPTS/P-02-meeting-notes-to-actions.md`, `05_PROMPTS/P-03-action-aging-summary.md`
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`
- **Pack index:** `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Governance envelope

- **Data category:** Synthetic.
- **Tool environment:** ATLAS-local Markdown; Personal AI tool acceptable for the AI-step exercise.
- **Review intensity:** Light for personal practice.
- **Per-domain review pattern:** Meeting notes to action items (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`).

## Demo purpose

Walk two paired workflows end-to-end: extract actions from fictional meeting notes (W-02 / P-02) and produce an aging summary that flags ownership gaps and overdue items (W-03 / P-03). Both halves run against the same Project Northstar Demo scenario.

## Part 1 — Meeting notes to actions

### Step 1 - Synthetic meeting notes

Friday week-2 status meeting on Project Northstar Demo. Roughly 30 minutes. Notes captured by Reporting Coordinator.

```text
Synthetic meeting notes — 2026-05-15 — Project Northstar Demo

Attendees: PM/Ops, Team Lead, Workstream A Lead, Workstream B Lead, Workstream C Lead, Reporting Coordinator.

Discussion:
- Weekly status template is approved by Workstream A Lead and ready for the week 3 cycle.
- Action tracker prototype is two days late; Workstream B Lead said the delay was owner-availability for confirming assignments, not the tool itself.
- Three actions from last week were closed; two new actions were opened during the call but only one had a date.
- Decision log section was added to the meeting template; the team will use it starting next meeting.
- Risk R-001 (action owners not confirmed) is still open; Team Lead agreed to make owner/date confirmation a meeting-close requirement.
- Workstream C Lead asked whether the risk-review workshop on 2026-05-20 should also cover the recurring "missing decision rationale" theme; PM/Ops will confirm by 2026-05-18.
- Lessons learned first draft will need pilot feedback; pilot is currently late by two days, which will likely push the draft.
```

### Step 2 - AI step (P-02 invocation pattern)

Tom runs `P-00-safety-precheck.md`: Synthetic, Personal AI tool, Tom as reviewer, paired W-02. Clear.

Tom sends the notes through P-02 with placeholders filled (`[SYNTHETIC_MEETING_TITLE]`, `[SYNTHETIC_DATE]`, `[PLACEHOLDER_OWNER]`).

### Step 3 - AI draft action list (before review)

| Action ID | Action | Owner | Due date | Source line | Notes |
|---|---|---|---:|---|---|
| A-101 | Apply approved weekly status template to the week 3 cycle. | Reporting Coordinator | 2026-05-22 | "Weekly status template is approved by Workstream A Lead and ready for the week 3 cycle." | Inferred due date from "week 3 cycle"; AI flags for owner confirmation. |
| A-102 | Confirm owner/date discipline at meeting close. | Team Lead | (missing field) | "Team Lead agreed to make owner/date confirmation a meeting-close requirement." | No date in source; AI flags missing field. |
| A-103 | Decide whether the 2026-05-20 risk-review workshop should also cover "missing decision rationale." | PM/Ops | 2026-05-18 | "PM/Ops will confirm by 2026-05-18." | Date in source. |
| A-104 | Start using the decision-log section in the meeting template. | Team Lead | 2026-05-22 (next meeting) | "the team will use it starting next meeting." | AI flags "next meeting" — needs explicit date. |
| A-105 | Convert R-001 (action owners not confirmed) mitigation into the meeting-close requirement. | PM/Ops | (missing field) | "Risk R-001 ... is still open" + "owner/date confirmation a meeting-close requirement." | AI flags missing date and owner clarity (could also be Team Lead). |
| A-106 | Provide pilot feedback to feed lessons-learned first draft. | Workstream B Lead | (missing field) | "Lessons learned first draft will need pilot feedback." | AI flags missing field. |

AI's structured findings appended below the table:

- Three actions are missing a date (A-102, A-105, A-106). The AI did not invent dates.
- One action has ambiguous ownership (A-105 — PM/Ops or Team Lead). AI flagged; Tom or the named human decides.
- Two new actions from the call (mentioned in the notes as "two new actions were opened during the call but only one had a date") were not present in the notes themselves. The AI flagged this as a source gap rather than inventing the actions.

### Step 4 - Human review (Meeting notes to action items pattern)

Per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Meeting notes to action items":

- **Every action has an owner and a date?** No — A-102, A-105, A-106 missing dates; A-105 ambiguous owner. AI correctly flagged rather than invented.
- **Owner has been informed?** Tom confirms by walking back to attendees on the two ambiguous items before the tracker is updated.
- **Action is what the owner agreed to, not what AI inferred?** A-101's "week 3 cycle" → 2026-05-22 needs Reporting Coordinator confirmation that the date is correct.

### Step 5 - Final action list (after review)

Tom resolves the flags before the tracker is updated:

| Action ID | Action | Owner | Due date | Status |
|---|---|---|---:|---|
| A-101 | Apply approved weekly status template to the week 3 cycle. | Reporting Coordinator | 2026-05-22 | Open |
| A-102 | Confirm owner/date discipline at meeting close. | Team Lead | 2026-05-22 | Open |
| A-103 | Decide whether the 2026-05-20 risk-review workshop should also cover "missing decision rationale." | PM/Ops | 2026-05-18 | Open |
| A-104 | Start using the decision-log section in the meeting template. | Team Lead | 2026-05-22 | Open |
| A-105 | Convert R-001 mitigation into the meeting-close requirement. | Team Lead | 2026-05-22 | Open |
| A-106 | Provide pilot feedback to feed lessons-learned first draft. | Workstream B Lead | 2026-05-29 | Open |

Tom resolved A-105's ambiguity by talking to Team Lead and PM/Ops outside the meeting; the AI did not commit either party.

## Part 2 — Action aging summary

### Step 1 - Synthetic action tracker snapshot

Tracker state at the week-3 cutoff (2026-05-22). Each row carries today's date for aging calculations.

| Action ID | Action | Owner | Due date | Status | Today | Age (days from due) | Last touched |
|---|---|---|---:|---|---:|---:|---:|
| A-001 | Finalize weekly status template. | PM/Ops | 2026-05-13 | Complete | 2026-05-22 | -9 | 2026-05-13 |
| A-002 | Confirm owners for open actions. | PM/Ops | 2026-05-16 | Open | 2026-05-22 | +6 | 2026-05-20 |
| A-003 | Draft decision log format. | PM/Ops | 2026-05-17 | Open | 2026-05-22 | +5 | 2026-05-18 |
| A-004 | Review risk wording with team lead. | Team Lead | 2026-05-20 | Not started | 2026-05-22 | +2 | 2026-05-15 |
| A-101 | Apply approved weekly status template to week 3 cycle. | Reporting Coordinator | 2026-05-22 | Open | 2026-05-22 | 0 | 2026-05-21 |
| A-102 | Confirm owner/date discipline at meeting close. | Team Lead | 2026-05-22 | Open | 2026-05-22 | 0 | 2026-05-20 |

### Step 2 - AI step (P-03 invocation pattern)

Tom runs `P-00-safety-precheck.md`. Sends the table through P-03.

### Step 3 - AI aging summary (before review)

```text
Action aging summary — Project Northstar Demo — 2026-05-22

Overdue (Aging > 0):
- A-002 (+6) — Confirm owners for open actions. Owner: PM/Ops. Reason for aging (observation): action depends on multi-party confirmation; no follow-up entries in the last 2 days.
- A-003 (+5) — Draft decision log format. Owner: PM/Ops. Reason for aging (observation): single-owner task; no progress notes since 2026-05-18.
- A-004 (+2) — Review risk wording with team lead. Owner: Team Lead. Reason for aging (observation): not started; last touched 2026-05-15, before the due date.

Due today:
- A-101 (0) — Apply weekly status template to week 3 cycle. Owner: Reporting Coordinator.
- A-102 (0) — Confirm owner/date discipline at meeting close. Owner: Team Lead.

Closed within window: A-001.

Neutral follow-up drafts (Tom to send or not, after review):
- To PM/Ops on A-002 / A-003: "Confirming where these stand. If a blocker exists, name it and the next step; if not, share a target date to keep aging visible."
- To Team Lead on A-004: "Reviewing whether the 2026-05-20 due date is still right, or whether the action should be re-scoped post-workshop."

Hygiene notes:
- Two actions (A-002, A-003) have the same owner and similar aging; consider whether they are blocked by the same dependency.
- No actions missing an owner or a date in this snapshot. (Earlier snapshots flagged missing fields; the prior round of cleanup has reduced that to zero.)
```

### Step 4 - Human review (Meeting notes to action items / Risk and issue triage hybrid)

- AI correctly classified by aging and gave reasons as observations, not conclusions.
- AI did not assign a severity, did not change owners, did not commit a recovery date.
- AI's follow-up drafts are neutral and ask for status; they do not paraphrase or pressure.
- Tom decides whether to send the drafts and whether to add a hygiene note about the PM/Ops bottleneck on A-002/A-003.

### Step 5 - Final aging summary (after review)

Same as AI draft, plus Tom's added line:

```text
PM/Ops bottleneck note: A-002 and A-003 are both PM/Ops-owned and both aged. PM/Ops to confirm a single re-prioritization rather than running both in parallel; revisit at next 1:1.
Reviewer sign-off: Tom (Light intensity, synthetic input), 2026-05-23.
```

## Demo value

This demo illustrates two AI moves on the same data: extraction (W-02 / P-02) and aging (W-03 / P-03). In both halves the AI flags rather than invents — missing dates, ambiguous ownership, single-owner bottlenecks — and Tom resolves before the tracker is updated. The pattern scales to real meetings only after re-approval per the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`; the demo's structural shape carries forward unchanged.

## Cross-references

- Paired workflow cards: `04_WORKFLOWS/W-02-meeting-notes-to-actions.md`, `04_WORKFLOWS/W-03-action-item-aging.md`.
- Paired prompt cards: `05_PROMPTS/P-02-meeting-notes-to-actions.md`, `05_PROMPTS/P-03-action-aging-summary.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0024.
