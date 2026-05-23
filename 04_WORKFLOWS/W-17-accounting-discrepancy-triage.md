# W-17-accounting-discrepancy-triage - Accounting discrepancy triage workflow

## Workflow identity

- **ID:** W-17
- **Backlog ID:** A-0056
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Accounting discrepancy triage workflow.

## 2. PM/Ops problem addressed

Project accounting discrepancies (between EVM, ledger, time-tracking, and reporting narratives) accumulate as informal "we'll figure it out later" items. Without a triage path, the same discrepancy resurfaces every reporting period, leadership loses confidence in the numbers, and the accounting reviewer becomes the bottleneck for every clarification. The team can describe the discrepancy but not the next concrete step or its owner.

## 3. Intended outcome

A short triage record for each accounting discrepancy with: a one-line description, the affected views, the impact on the period's reporting, the named owner (accounting reviewer or designated analyst), the next concrete step, the expected resolution date, and a status. Tom does the assigning; AI structures, names blind spots, and proposes investigation questions. The triage record feeds the next reconciliation narrative (`W-09`) so the discrepancy does not disappear silently.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real accounting discrepancies are Employer-approved at best and route only to an Employer-approved AI tool with explicit scope approval.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for accounting content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real accounting discrepancy.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Finance, EVM, and project accounting outputs.

## 5. Safe inputs

- Synthetic discrepancy notes (`08_SYNTHETIC_DEMOS/SYNTHETIC_ACCOUNTING_RECONCILIATION_DEMO.md` and the four-view spread it surfaces).
- Generic project-accounting examples from public PMI / EVM / project-controls material.
- Tom's own notes from public training or his own non-restricted observations.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real project-accounting ledger entries, real labor extracts, real EVM ACWP, real burden-rate detail, real overhead allocations.
- Real customer billing, contract clauses, payment terms, or vendor invoices.
- Real cost-account codes, WBS codes, or program identifiers.
- Anything that would not be acceptable inside the personal-preparation boundary in `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.

## 7. Output format

A Markdown triage table:

| # | One-line description | Affected views | Period impact | Owner | Next step | Target date | Status (open / in progress / blocked / closed) | Notes |
|---|---|---|---|---|---|---|---|---|

Plus, below the table:

- **Affected-views legend** — naming the four typical views (EVM ACWP, project accounting ledger, time-tracking, reporting narrative) and any program-specific additions noted in the synthetic demo.
- **Investigation candidates** — discrepancies where the next step is "investigate" rather than "fix"; AI may propose investigation questions but not conclusions.
- **Open ownership** — discrepancies with no clear owner; Tom assigns before the triage record is used.
- **Tracking note** — the triage record feeds the next reconciliation narrative so each open item has a visible path to closure.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic input. Same workflow runs unchanged in an Employer-approved AI tool against approved accounting content; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom for synthetic practice. For real accounting discrepancies, the accounting reviewer or designated finance analyst is the accountable approver of each triage record. Review intensity from §4 applies. Reviewer follows the "Finance, EVM, and project accounting outputs" pattern: recompute key numbers, confirm units and periods, confirm narrative does not state causes the data does not justify, confirm output does not present AI inference as accounting fact.

## 10. Step-by-step process

1. **Classify the input.** Confirm all inputs are Synthetic, Public, or Tom-personal. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Collect the discrepancies.** Pull each item from the reconciliation narrative (`W-09`) output and any side notes from the period close. Each discrepancy starts as a row in the triage table with description and affected views populated.
4. **AI structuring step.** Send the rough list through the AI step (Personal AI tool for Synthetic; Employer-approved AI tool when approved). AI proposes investigation questions, identifies likely cause categories from the W-09 patterns, and flags missing fields. AI does not assign owners, severity, or financial cause.
5. **Owner assignment.** Tom assigns the owner from a short list (accounting reviewer, finance analyst, time-tracking owner, EVM analyst, status-pack author). Owners that span multiple roles get one named primary plus the supporting roles in the Notes column.
6. **Next-step and target-date assignment.** Tom (with the owner) names the next concrete step and a target date. "Investigate" is acceptable as a next step when the investigation question is named.
7. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
8. **Tracking handoff.** The triage record is the input to the next period's reconciliation narrative; each row marked `open` or `in progress` gets a status update in the next narrative.
9. **Record sign-off.** Standard intensity: sign-off line on the triage record. Strict intensity (real data): sign-off plus a record of source, tool, reviewer, accountable owner, and date inside the approved employer venue.

## 11. Quality checks

Good output:
- Every discrepancy row has a named owner.
- Affected-views column lists the specific views in conflict (not "everywhere").
- Next-step column names a concrete action ("confirm time-tracking cutoff date with payroll") rather than a verb-only stub ("review").
- Target-date column names a date or "by next reconciliation."
- Investigation candidates are listed separately so the reviewer can decide whether to pull them into the next period.

Red flags:
- AI asserted a cause (e.g., "ledger total is wrong"). Re-frame as an investigation question.
- A discrepancy with no owner gets carried forward unchanged for more than one period. Force assignment before the next close.
- A "closed" discrepancy has no entry naming what changed and who confirmed it. Reopen and ask the owner.

## 12. Audit and logging notes

For synthetic practice, the audit trail is the repo's commit history plus the triage record itself.

For real accounting discrepancies, the audit trail includes the source extracts referenced, the tool used (Employer-approved AI tool, named), the reviewer and accountable owner, the date the triage record was approved, and the link between this triage record and the prior / next reconciliation narrative. The triage record lives in the approved employer venue; it does not live in ATLAS.

## 13. Failure modes and escalation triggers

Failure modes:
- The same discrepancy reappears in three consecutive periods unchanged. Stop iterating; escalate to the accounting reviewer.
- The AI step asserts a financial cause ("the ledger over-states cost by 25 units"). Reviewer rewrites as an observation and an investigation question.
- An owner declines the assignment without naming an alternative. Stop; route to PM/Ops to negotiate the owner.
- A discrepancy is marked closed without a confirmation source. Reopen.

Escalation triggers (stop iterating the AI draft, go to a human):
- Discrepancy magnitude exceeds the program's documented reconciliation tolerance — escalate to the accounting reviewer or finance lead, not to AI.
- Discrepancy implies a financial-system error (e.g., posting against the wrong control account) — escalate per the program's defect-reporting process.
- Discrepancy implies a policy violation (e.g., unapproved scope being charged to the period) — escalate per the program's compliance process; do not paraphrase into a personal AI tool.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Runs against the Phase 9 synthetic demo (`SYNTHETIC_ACCOUNTING_RECONCILIATION_DEMO.md`). ATLAS-local Markdown; reviewer is Tom; review intensity Standard.
- **Post-approval form:** Same workflow structure; data category shifts to Employer-approved; tool environment shifts to the specific Employer-approved AI tool; review intensity shifts to Strict; accountable approver is the accounting reviewer or designated analyst; the triage record lives in the approved employer venue.
- **Re-approval triggers:** Any movement from synthetic to real discrepancies; any change of tool; any new view added to the reconciliation that is not already on the approved list. Each requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0056.
- Paired Phase 5 prompt: none dedicated. P-09 (accounting reconciliation narrative) and P-08 (issue and discrepancy triage) cover the AI-drafting steps this workflow draws on; the triage record itself is a structural Markdown table rather than an AI-drafting target.
- Related Phase 9 artifacts: `08_SYNTHETIC_DEMOS/SYNTHETIC_EVM_WORKBOOK.md` (A-0054 substrate); `08_SYNTHETIC_DEMOS/SYNTHETIC_ACCOUNTING_RECONCILIATION_DEMO.md` (A-0055 walkthrough that produces the discrepancies this workflow tracks).
- Related workflows: `04_WORKFLOWS/W-08-issue-and-discrepancy-triage.md` (generic issue triage; this workflow is its accounting-specific sibling); `04_WORKFLOWS/W-09-accounting-reconciliation-narrative.md` (produces the discrepancies); `04_WORKFLOWS/W-13-cross-tool-mismatch-investigation.md` (broader cross-tool pattern).
- Workflow library index: `04_WORKFLOWS/WORKFLOW_LIBRARY.md`.
- Decision log: D-0052..D-0054 (Phase 9 set).
