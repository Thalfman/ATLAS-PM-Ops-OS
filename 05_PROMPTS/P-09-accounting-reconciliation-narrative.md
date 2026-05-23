# P-09-accounting-reconciliation-narrative - Project accounting reconciliation narrative support

## Prompt identity

- **ID:** P-09
- **Paired workflow:** W-09 (`04_WORKFLOWS/W-09-accounting-reconciliation-narrative.md`)
- **Backlog ID:** A-0019
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Draft a short period-close reconciliation narrative that walks the discrepancy in a consistent structure: what views disagree, what each view shows, what the apparent driver is (as observation, not conclusion), what the investigation path is, and who owns the next step. The prompt addresses W-09 §2: defensive, vague reconciliation language and AI-invented accounting causes. The deliverable is the six-section narrative described in W-09 §7 (Reconciliation scope, What each view shows, Apparent driver, Investigation path, Owner and next step, Open questions).

## 2. Paired workflow and PM/Ops role

Paired with `W-09-accounting-reconciliation-narrative.md`. Executes step 4 of the W-09 §10 process ("Ask AI to identify discrepancies, not explain"). AI role: identify discrepancies between the four views (schedule, labor, accounting, reporting) and structure the discrepancy as a narrative grounded only in the provided numbers. AI must not name accounting causes the data does not support and must not make accounting determinations.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real reconciliation data is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for accounting content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real reconciliation.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Finance, EVM, and project accounting outputs.

## 4. Safe input requirements

Mirror W-09 §5:

- Synthetic cost categories with fictional period-close numbers.
- Generic reconciliation examples and fictional mismatches.
- Tom's own notes from public project-accounting training.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-09 §6:

- Real accounting exports, real labor data, real cost categories from any employer system without explicit approval.
- Real contract value, fee, or rate detail.
- Real customer billing or invoicing detail.
- Restricted financial detail at any level.

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[SYNTHETIC_PERIOD]` — fictional period (e.g., "Period closing 2026-06-30").
- `[APPROVED_INPUT]` — the four-view snapshot block (headline numbers from schedule view, labor view, accounting view, reporting view for the same period and scope).
- `[PLACEHOLDER_OWNER]` — fictional investigation-owner names.
- `[FICTIONAL_VARIANCE]` — the headline discrepancy figure.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional draft a project accounting reconciliation narrative.

ROLE
- Identify discrepancies between the four views provided.
- Frame apparent drivers as observations of what the data shows.
- Do not name accounting causes the data does not support.
- Do not make accounting determinations.
- Do not propose a closing posture before investigation has occurred.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Period: [SYNTHETIC_PERIOD]
- Headline discrepancy: [FICTIONAL_VARIANCE]
- Four-view snapshot (each view shows the headline numbers for the same period and scope):
[APPROVED_INPUT]
- Known investigation owners: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown narrative with these sections, in this order:

1. **Reconciliation scope** — one paragraph naming the period, the views being compared, and the headline discrepancy.
2. **What each view shows** — small Markdown table with one row per view (schedule, labor, accounting, reporting) and the headline numbers. Units and period explicit.
3. **Apparent driver (observed, not asserted)** — 1-3 bullets framing what the data suggests as observations.
4. **Investigation path** — 1-3 bullets naming who to ask and what to verify.
5. **Owner and next step** — named owner from the inputs, concrete next step, target date.
6. **Open questions** — 0-3 bullets.

DISCIPLINE
- Every headline number in the table must recompute against the source view value. If a number does not match, do not include it; flag it as "view value not matched" in a footnote.
- Reframe causes as observations: convert "Team Y under-charged" into "labor view shows X hours; accounting view shows Y hours; gap of Z hours; investigation needed."
- Investigation owner must come from the inputs. If no owner exists, write "owner not assigned; assignment pending" — do not invent.
- Period and scope must be identical across all four view rows; if they are not, flag a period-or-scope mismatch.
- Append a "Number trace" list: each table value mapped back to the source view value.

Return the narrative and the number trace only.
```

## 8. Expected output

A Markdown narrative with six labeled sections plus a four-row view-comparison table, followed by a "Number trace" list. Total body roughly 200-350 words. Mirrors W-09 §7.

## 9. Human review checklist

The reviewer (Tom; finance lead or project controls lead for employer-deployable runs) follows the "Finance, EVM, and project accounting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before using the output:

- Recompute the key numbers against source data.
- Confirm units and periods match across all four views.
- Confirm narrative does not state causes the data does not justify.
- Confirm the output does not present AI inference as accounting fact.
- Confirm investigation owner and target date are real and confirmed.
- Confirm no closing posture is proposed before investigation has occurred.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-09 §13):

- AI presents inferred cause as accounting fact.
- Numbers do not recompute.
- AI proposes a closing posture before investigation has occurred.
- Investigation owner unconfirmed or generic ("team").
- Reviewer signs off without recomputing.

Escalation triggers:

- Discrepancy crosses into customer billing, contract, or audit territory — go to finance lead.
- Discrepancy materially affects EAC or program forecast — go to program manager.
- Reconciliation data turns out to be Prohibited — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic four-view snapshot, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real four-view data, Employer-approved AI tool against approved scope, Strict review (recompute every number; remove every inferred cause), accountable owner is finance lead, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," stored in approved venue.
- **Re-approval triggers:** Broadening scope from narrative support to accounting determination; including contract or customer-billing detail; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm all four view values are synthetic for personal-preparation runs.
- Confirm cost categories do not map to real contract line items.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before sign-off. Required for Strict review intensity.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-09-accounting-reconciliation-narrative.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0019.
- Related artifacts: A-0055 Project Accounting Reconciliation Walkthrough (Phase 9), A-0056 Accounting Discrepancy Triage Workflow (Phase 9).
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-05-schedule-variance-narrative.md`, `P-06-evm-variance-explanation.md`.
