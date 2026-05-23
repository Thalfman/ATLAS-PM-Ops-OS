# W-06-evm-variance-explanation - EVM variance explanation support

## Workflow identity

- **ID:** W-06
- **Backlog ID:** A-0066
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

EVM variance explanation support.

## 2. PM/Ops problem addressed

EVM variance explanations frequently fail one of three ways: vague ("schedule challenges"), inconsistent week to week (different framings for the same number), or disconnected from corrective action (the variance is described but the response is not). When AI is used to draft the explanation without guardrails, it invents causes the EVM data does not justify.

## 3. Intended outcome

A draft variance explanation that names CV, SV, CPI, and SPI accurately, walks cause-impact-corrective-action in a consistent structure, and does not state causes the underlying data does not justify. Numbers traceable to the source EVM dataset; corrective actions reference real, owned activities.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real EVM data is Employer-approved and routes only to an Employer-approved AI tool with explicit scope approval.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only when both the EVM data and the tool have explicit approval.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real EVM narrative.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Finance, EVM, and project accounting outputs.

## 5. Safe inputs

- Synthetic EVM dataset (BCWS, BCWP, ACWP, CV, SV, CPI, SPI, EAC, ETC) for a fictional project.
- Generic CPI/SPI examples and fictional variance drivers.
- Tom's own notes from public EVM training.
- Generic corrective-action patterns from public PMI material.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real EVM datasets, real cost or schedule values from employer systems.
- Real contract value, fee structure, or customer-funded categories.
- Real cause attribution to people, teams, vendors, or customers.

## 7. Output format

A short Markdown narrative with these sections:

1. **Metrics snapshot** - small table with BCWS, BCWP, ACWP, CV, SV, CPI, SPI, EAC (period and cumulative).
2. **What the metrics show** - 2-4 bullets, plain-language description of what the numbers say, no causes yet.
3. **Cause (observed, not asserted)** - 1-3 bullets framing apparent drivers as observations of what the data and the schedule show; attribute any real cause to a named accountable owner.
4. **Impact** - 1-2 bullets on the implications (EAC pressure, schedule pressure, customer-visible impact).
5. **Corrective action** - 1-3 bullets naming a real, owned activity; never AI-generated commitments.
6. **Open items / decisions needed** - 0-3 bullets.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with a synthetic EVM dataset. The same workflow runs unchanged in an Employer-approved AI tool against an approved real EVM dataset; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. The accountable owner is the finance lead, program controls lead, or program manager. Review intensity from §4 applies. Reviewer follows the "Finance, EVM, and project accounting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: recompute the key numbers, confirm units and periods match, confirm narrative does not state causes the data does not justify, confirm the output does not present AI inference as accounting fact.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide the EVM snapshot.** Paste BCWS, BCWP, ACWP, CV, SV, CPI, SPI, EAC for the period and cumulative.
4. **Ask AI to structure cause-impact-corrective-action.** Prompt the AI to produce the §7 narrative. Forbid the AI from naming a cause not supported by the data. Forbid the AI from inventing corrective actions.
5. **Recompute every number.** CV = BCWP - ACWP. SV = BCWP - BCWS. CPI = BCWP / ACWP. SPI = BCWP / BCWS. EAC formulas as agreed by the program (BAC/CPI is common). Any number that does not recompute is replaced.
6. **Strip cause overclaims.** Replace asserted causes ("Team Y underperformed") with observations ("BCWP is 15% below BCWS for activities in WBS X; schedule shows starts later than planned"). Attribute any real cause to a named owner.
7. **Confirm corrective action.** Every corrective-action bullet must point to a real activity with a real owner. If none exists, the bullet says "no corrective action yet identified; decision pending [owner]."
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every metric recomputes from the source.
- Causes are framed as observations or attributed to a named owner.
- Corrective actions name real activities and real owners.
- Period and cumulative numbers are labeled.
- Narrative is short and reads even.

Red flags:
- AI-inferred causes presented as accounting fact.
- Numbers that do not recompute.
- Corrective actions invented to fill the section.
- Unit or period mismatches (period CPI compared to cumulative SPI).
- Confidence language ("we expect to recover by") without a supporting activity.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": EVM snapshot, tool, operator, reviewer (finance or program controls), accountable owner (program manager), date, outcome, storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI presents inference as accounting fact.
- Numbers do not recompute against the snapshot.
- Corrective actions are AI-generated rather than program-owned.
- Variance smoothed by selective period comparison.
- Reviewer signs off without recomputing.

Escalation triggers (stop iterating the AI draft, go to a human):
- The real cause involves contract, customer, or compliance matters - go to program lead and finance lead.
- EAC pressure exceeds approved tolerance - go to finance lead.
- The data turns out to span Prohibited content (customer fee structure, contract details) - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic EVM dataset, Personal AI tool, Standard review, sign-off line. Tom drafts; finance and program controls are accountable.
- **Employer-deployable form (after approval):** Real EVM data, Employer-approved AI tool against approved scope, Strict review (recompute every metric; remove every inferred cause), accountable owner is program manager and finance lead, full audit envelope, stored in approved venue.
- **Re-approval triggers:** Broadening scope from variance explanation to forecast modeling; including contract-value detail; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0066.
- Paired Phase 5 prompt: A-0018 EVM Variance Explanation Support Prompt (TBD in Phase 5).
- Related artifacts: A-0054 Synthetic EVM Workbook (Phase 9).
- Related workflows: W-05 (schedule variance narrative), W-09 (accounting reconciliation), W-13 (cross-tool mismatch).
