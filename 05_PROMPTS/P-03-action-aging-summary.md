# P-03-action-aging-summary - Action aging summary and follow-up drafts

## Prompt identity

- **ID:** P-03
- **Paired workflow:** W-03 (`04_WORKFLOWS/W-03-action-item-aging.md`)
- **Backlog ID:** A-0041
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Classify open action items by aging condition (overdue, blocked, ambiguous, duplicate, dependency-heavy, on-track, missing field) and produce a neutral, owner-tagged follow-up draft for the rows that warrant follow-up. The prompt addresses W-03 §2: actions accumulating silently, ambush-feeling late follow-up, and blame-tinged communication. The deliverable is the two-part output described in W-03 §7 (aging summary table plus per-row 3-5 sentence neutral drafts).

## 2. Paired workflow and PM/Ops role

Paired with `W-03-action-item-aging.md`. Executes steps 4-5 of the W-03 §10 process: classify aging and draft follow-ups in neutral tone. AI role: classify each row and draft a per-row follow-up message. AI must not invent missing data, recommend escalation based on aging alone, or volunteer to send messages.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for Tom's own action tracker entries with no employer-restricted content.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first). Employer-approved AI tool when the action tracker is employer business and the tool is approved.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for personal preparation. Strict for any follow-up message that will leave Tom's hands.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Meeting notes to action items (closest match; same accountability discipline applies to follow-up).

## 4. Safe input requirements

Mirror W-03 §5:

- Synthetic action tracker with fictional owners, dates, and statuses.
- Tom's own personal action notes from public meetings or his own preparation.
- Aging actions in a generic, fictional project context for practice.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-03 §6:

- Real employer action trackers, real owner names, real internal due dates, or real internal program references unless the tracker and tool are both approved.
- Action items that reveal restricted program structure, customer identities, contract obligations, or financial commitments.
- Aging analysis on prohibited-data trackers — no AI use; revert to manual review.

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[SYNTHETIC_AS_OF_DATE]` — fictional "as of" date for aging calculation.
- `[APPROVED_INPUT]` — the action tracker snapshot pasted as a Markdown table including original due dates and current status.
- `[PLACEHOLDER_OWNER]` — fictional owner names from the tracker.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional review aging action items and draft neutral follow-up messages.

ROLE
- Classify each row by aging condition.
- Draft one short, neutral follow-up message per row that warrants follow-up.
- Do not invent missing data; label gaps as "missing field."
- Do not use blame language ("you missed," "you're late").
- Do not propose escalation; suggest "consider escalation" only with a stated trigger.
- Do not offer to send the messages.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- As-of date: [SYNTHETIC_AS_OF_DATE]
- Action tracker snapshot (Markdown table with at minimum: #, Action, Owner, Original due date, Status, Notes):
[APPROVED_INPUT]
- Known owners and recent context: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

PART 1 — Aging summary table

| # | Action | Owner | Original due date | Days overdue | Blocker / dependency | Recommended next step | Aging classification |
|---|---|---|---|---|---|---|---|

Aging classification values (use exactly one per row): overdue, blocked, ambiguous, duplicate, dependency-heavy, on-track, missing field.

PART 2 — Follow-up drafts

For each row classified as overdue, blocked, ambiguous, or dependency-heavy, produce a 3-5 sentence Markdown block addressed to the named owner:

### Follow-up draft for row #N — [Owner]

[3-5 sentences. Names the action and original due date. Acknowledges the owner's context.
Asks one clear question or proposes one next step. No blame language. No escalation threats.
No presumptions about owner intent.]

DISCIPLINE
- If an aging field cannot be determined from the tracker (e.g., no original due date), set Days overdue to "missing field" and aging classification to "missing field."
- Do not recommend escalation unless the tracker shows a stated escalation trigger (repeated no-response, structural blocker, owner reassignment requested).
- Do not draft follow-ups for rows classified on-track or missing field.
- Duplicate rows: classify the second row as "duplicate" with a Note pointing to the first row; do not draft a follow-up for duplicates.

Return Part 1 and Part 2 and nothing else.
```

## 8. Expected output

Part 1: a Markdown table with eight columns including aging classification. Part 2: per-row neutral follow-up drafts of 3-5 sentences each, addressed to the named owner. Mirrors W-03 §7.

## 9. Human review checklist

The reviewer (Tom) follows the "Meeting notes to action items" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` (closest per-domain match per W-03 §4) and runs the post-flight checklist before sending anything:

- Confirm every row has a stated aging classification with a reason traceable to the tracker.
- Confirm "missing field" appears wherever the tracker did not have data, instead of an AI guess.
- Confirm follow-up drafts are short, neutral, and addressed to a named owner.
- Confirm drafts ask one question or propose one next step.
- Confirm no draft implies escalation without a stated trigger.
- Tom (not the AI) decides whether any row warrants escalation to a manager.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-03 §13):

- AI flags an action overdue when its due date was never set.
- Follow-up drafts that imply ownership Tom does not have.
- AI recommends escalation based on aging alone, without context.
- Drafts that disclose restricted information to an external owner.
- Reviewer accepts the table without checking the owner field.

Escalation triggers:

- An aging action turns out to be in someone else's tracker — go to the actual owner.
- A blocker is structural (resource, authority, dependency) — go to manager.
- Repeated overdue from the same owner with no response — go to manager with a neutral framing, not via the AI tool.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic or Tom-personal tracker, Personal AI tool, Standard review, sign-off line in the output. Tom drafts; Tom decides; nothing leaves the tool.
- **Employer-deployable form (after approval):** Approved-content tracker, Employer-approved AI tool against approved scope, Strict review, owner-confirmation step before any follow-up is sent through an approved channel, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums."
- **Re-approval triggers:** New tracker scope, new owner population, new channel for follow-ups, automated sending of any kind. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm the tracker snapshot does not include real owner names from employer systems for personal-preparation runs.
- Confirm no row references restricted program structure, customer detail, or contract obligations.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before any follow-up is sent. Required if any draft will be sent (Strict).

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-03-action-item-aging.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0041.
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-02-meeting-notes-to-actions.md`, `P-08-issue-and-discrepancy-triage.md`.
