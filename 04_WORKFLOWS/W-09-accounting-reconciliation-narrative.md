# W-09-accounting-reconciliation-narrative - Project accounting reconciliation narrative support

## Workflow identity

- **ID:** W-09
- **Backlog ID:** A-0036
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Project accounting reconciliation narrative support.

## 2. PM/Ops problem addressed

Period-close reconciliations between the schedule view, the labor view, the accounting view, and the reporting view routinely produce discrepancies that get described in vague, defensive language ("variance is being investigated") rather than as a clear, neutral, structured narrative the program can act on. AI used naively will invent accounting causes the data does not justify.

## 3. Intended outcome

A short reconciliation narrative that walks the discrepancy in a consistent structure: what views disagree, what each view shows, what the apparent driver is (as an observation, not a conclusion), what the investigation path is, and who owns the next step. The narrative does not let AI make accounting determinations.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real reconciliation data is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for accounting content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real reconciliation.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Finance, EVM, and project accounting outputs.

## 5. Safe inputs

- Synthetic cost categories with fictional period-close numbers.
- Generic reconciliation examples and fictional mismatches.
- Tom's own notes from public project-accounting training.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real accounting exports, real labor data, real cost categories from any employer system without explicit approval.
- Real contract value, fee, or rate detail.
- Real customer billing or invoicing detail.
- Restricted financial detail at any level.

## 7. Output format

A short Markdown narrative with these sections:

1. **Reconciliation scope** - one paragraph naming the period, the views being compared, and the headline discrepancy.
2. **What each view shows** - small table with one row per view (schedule, labor, accounting, reporting) and the headline numbers.
3. **Apparent driver (observed, not asserted)** - 1-3 bullets framing what the data suggests as observations.
4. **Investigation path** - 1-3 bullets naming who to ask and what to verify.
5. **Owner and next step** - named owner, concrete next step, target date.
6. **Open questions** - 0-3 bullets.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic reconciliation data. Same workflow runs unchanged in an Employer-approved AI tool against approved reconciliation data; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. The accountable owner is the finance lead or project controls lead. Nothing AI generates is an accounting determination. Review intensity from §4 applies. Reviewer follows the "Finance, EVM, and project accounting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: recompute the key numbers, confirm units and periods match, confirm narrative does not state causes the data does not justify, confirm the output does not present AI inference as accounting fact.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide the four views.** Paste headline numbers from each view (schedule, labor, accounting, reporting) for the same period and scope.
4. **Ask AI to identify discrepancies, not explain.** Prompt the AI to produce the §7 narrative grounded only in the provided numbers. Forbid the AI from naming an accounting cause not supported by the data.
5. **Recompute the headline numbers.** Confirm each view's number matches the source. Replace any AI guess.
6. **Reframe causes as observations.** Convert "Team Y under-charged" into "labor view shows X hours; accounting view shows Y hours; gap of Z hours; investigation needed."
7. **Assign investigation owner and date.** Real reconciliations have a real owner with a real target date; AI proposes, Tom confirms with the owner.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every headline number recomputes against the source view.
- Causes are framed as observations.
- Investigation path names who to ask and what to verify.
- Owner and next step are real and confirmed.
- Period and scope are explicit and consistent across views.

Red flags:
- AI-asserted accounting cause presented as fact.
- Numbers that do not recompute.
- Investigation owner unnamed or unconfirmed.
- Period or scope mismatch across views in the same narrative.
- Confidence language ("we expect to close by") without an investigation that supports it.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": four-view snapshot, tool, operator, reviewer (finance or project controls), accountable owner (finance lead), date, outcome, storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI presents inferred cause as accounting fact.
- Numbers do not recompute.
- AI proposes a closing posture before investigation has occurred.
- Investigation owner unconfirmed or generic ("team").
- Reviewer signs off without recomputing.

Escalation triggers (stop iterating the AI draft, go to a human):
- Discrepancy crosses into customer billing, contract, or audit territory - go to finance lead.
- Discrepancy materially affects EAC or program forecast - go to program manager.
- Reconciliation data turns out to be Prohibited - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic four-view snapshot, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real four-view data, Employer-approved AI tool against approved scope, Strict review (recompute every number; remove every inferred cause), accountable owner is finance lead, full audit envelope, stored in approved venue.
- **Re-approval triggers:** Broadening scope from narrative support to accounting determination; including contract or customer-billing detail; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0036.
- Paired Phase 5 prompt: P-09 Accounting Reconciliation Narrative (`05_PROMPTS/P-09-accounting-reconciliation-narrative.md`, backlog A-0019).
- Related artifacts: A-0055 Project Accounting Reconciliation Walkthrough (Phase 9), A-0056 Accounting Discrepancy Triage Workflow (Phase 9).
- Related workflows: W-06 (EVM variance explanation), W-13 (cross-tool mismatch).
