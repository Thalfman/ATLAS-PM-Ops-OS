# SYNTHETIC_ACCOUNTING_RECONCILIATION_DEMO.md

**SYNTHETIC DEMO. FICTIONAL ACCOUNTING RECONCILIATION. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0055
- **Phase:** 9 - EVM, Finance, and Project Accounting Track
- **Paired workflow card:** `04_WORKFLOWS/W-09-accounting-reconciliation-narrative.md`
- **Paired prompt card:** `05_PROMPTS/P-09-accounting-reconciliation-narrative.md`
- **Sibling Phase 9 substrate:** `08_SYNTHETIC_DEMOS/SYNTHETIC_EVM_WORKBOOK.md`
- **Sibling Phase 9 workflow:** `04_WORKFLOWS/W-17-accounting-discrepancy-triage.md`
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`
- **Pack index:** `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Governance envelope

- **Data category:** Synthetic.
- **Tool environment:** ATLAS-local Markdown; Personal AI tool acceptable for the AI-step exercise.
- **Review intensity:** Light for personal practice.
- **Per-domain review pattern:** Finance, EVM, and project accounting outputs.

## Demo purpose

Walk a project-accounting reconciliation narrative end-to-end against four fictional views of the same Project Northstar Demo period, surface the four-way mismatch using the W-09 / P-09 pattern, structure the discrepancy without asserting a financial cause, and propose investigation questions for the accounting reviewer.

## Step 1 - Synthetic input: four views, one period

Period: 2026-05-04 through 2026-05-22 (weeks 1-3). Project: Synthetic Project Northstar Demo. Numbers are illustrative round units; no currency.

| View | Source | Total cost reported for the period | Notes |
|---|---|---:|---|
| 1. EVM workbook | ACWP from `SYNTHETIC_EVM_WORKBOOK.md` | 435 | Status date 2026-05-22. |
| 2. Project accounting ledger | Synthetic ledger extract | 460 | Cutoff 2026-05-22 EOD. |
| 3. Time-tracking system | Synthetic labor hours × loaded rate | 410 | Cutoff 2026-05-19 EOD (early cutoff). |
| 4. Status pack narrative | Reported in the week-3 weekly status | "approximately 430" | No precise cutoff; narrative figure. |

Four numbers (435, 460, 410, "~430") for the same period. The reconciliation question is which figure is right, why they differ, and what follow-up is needed before the week-3 readout.

## Step 2 - AI step (P-09 invocation pattern)

Tom runs `P-00-safety-precheck.md`: Synthetic, Personal AI tool, Tom as reviewer, paired W-09. Clear. Sends the four-view table through P-09.

## Step 3 - AI reconciliation narrative (before review)

```text
Reconciliation narrative — Project Northstar Demo — period 2026-05-04 through 2026-05-22

Headline observation
Four views of the same period show four different totals: 435 (EVM ACWP), 460 (project accounting ledger), 410 (time-tracking), "approximately 430" (status pack narrative). The spread is 50 units (~12%) between the lowest and highest. No view can be assumed correct without confirming cutoff alignment, scope inclusion, and posting status.

Discrepancy structure (four-way)
- EVM ACWP (435) vs ledger (460): ledger is 25 units higher than EVM. Possible drivers: (a) ledger includes overhead burden not captured in EVM ACWP; (b) ledger includes late-posting entries the EVM cutoff did not pick up; (c) ledger captures items outside the control accounts in scope.
- EVM ACWP (435) vs time-tracking (410): time-tracking is 25 units lower than EVM. Likely cutoff alignment: time-tracking's 2026-05-19 cutoff misses three days of labor (2026-05-20, 21, 22).
- Time-tracking (410) vs ledger (460): time-tracking is 50 units lower than ledger. Combination of (a) the 3-day time-tracking cutoff gap and (b) ledger including non-labor or burden items.
- Status pack narrative ("~430") vs EVM ACWP (435): within rounding; narrative was likely derived from EVM ACWP minus rounding tolerance. The narrative figure is the least defensible without a source citation.

Likely cause categories (observations, not conclusions)
- Cutoff misalignment: time-tracking is the obvious case.
- Posting lag: ledger may include entries the EVM tool has not yet absorbed.
- Scope mismatch: ledger may include items outside the control-account structure in scope for this period.
- Rounding / narrative imprecision: status pack figure is a written approximation.

Investigation questions for the accounting reviewer
1. What is the time-tracking cutoff date for this period, and does the time-tracking total advance once the 2026-05-20/21/22 entries post?
2. Does the ledger total include overhead burden that EVM ACWP excludes? If yes, what is the burden rate or fixed overhead contribution?
3. Are there ledger entries for the period that are outside the three control accounts (CA-A, CA-B, CA-C)? If yes, are they in or out of scope for the reporting period?
4. Should the status pack narrative figure be replaced with the EVM ACWP figure (citing the cutoff) before the week-3 readout?
5. Is there a documented reconciliation procedure between EVM ACWP and project accounting ledger that names the expected difference?

What this narrative does not assert
- It does not call any view "right" or "wrong."
- It does not assign cost to any individual or workstream owner.
- It does not commit to a corrected total.
- It does not change any system of record.

Sign-off
- Drafted by [Tom] on [YYYY-MM-DD] (synthetic practice).
- Reviewed by [Tom for synthetic practice; accounting reviewer for real data] on [YYYY-MM-DD].
- Adjustments after review: [list or "none"].
```

## Step 4 - Human review (Finance, EVM, and project accounting outputs pattern)

Per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Finance, EVM, and project accounting outputs":

- **Recompute key numbers against source data.** Tom checks 460 − 435 = 25, 435 − 410 = 25, 460 − 410 = 50. Pass.
- **Confirm units and periods match.** The narrative notes the time-tracking cutoff difference explicitly. Pass.
- **Confirm narrative does not state causes the data does not justify.** AI framed causes as "possible drivers" and "likely cause categories" rather than assertions. Pass.
- **Confirm output does not present AI inference as accounting fact.** AI's investigation questions explicitly route the unresolved items to the accounting reviewer. Pass.

Tom's edit before sharing: tighten the headline observation to lead with the action requested ("the four-view spread needs accounting-reviewer follow-up before the week-3 readout") rather than the description.

## Step 5 - Final narrative (after review)

The AI draft above with the headline-observation lead tightened, and the sign-off block filled. The four investigation questions become the next step for the accounting reviewer and feed the discrepancy-triage workflow (`W-17`) for tracking.

## Demo value

This demo illustrates the four-view reconciliation pattern (W-09 §7): name each view, name the spread, structure the candidate drivers as observations, and route to the accounting reviewer with concrete questions. AI never picks the "right" view; AI never assigns cost to any team; AI never commits a corrected total. Migration to real reconciliation data requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`. The pattern transfers; the data category and tool environment shift.

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-09-accounting-reconciliation-narrative.md`.
- Paired prompt card: `05_PROMPTS/P-09-accounting-reconciliation-narrative.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Sibling Phase 9 substrate: `08_SYNTHETIC_DEMOS/SYNTHETIC_EVM_WORKBOOK.md` (source of the 435 EVM ACWP figure).
- Sibling Phase 9 workflow: `04_WORKFLOWS/W-17-accounting-discrepancy-triage.md` (tracks the investigation questions through to closure).
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0055.
