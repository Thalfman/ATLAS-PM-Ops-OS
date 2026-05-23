# P-06-evm-variance-explanation - EVM variance explanation support

## Prompt identity

- **ID:** P-06
- **Paired workflow:** W-06 (`04_WORKFLOWS/W-06-evm-variance-explanation.md`)
- **Backlog ID:** A-0018
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Draft an EVM variance explanation that walks cause-impact-corrective-action in a consistent structure, naming CV, SV, CPI, and SPI accurately and refusing to state causes the EVM data does not justify. The prompt addresses W-06 §2: explanations that are vague, inconsistent week to week, or disconnected from corrective action. The deliverable is the six-section narrative described in W-06 §7 (metrics snapshot, what the metrics show, cause observed not asserted, impact, corrective action, open items).

## 2. Paired workflow and PM/Ops role

Paired with `W-06-evm-variance-explanation.md`. Executes step 4 of the W-06 §10 process ("Ask AI to structure cause-impact-corrective-action"). AI role: structure the EVM snapshot into the §7 narrative; refuse to name causes not supported by the data; refuse to invent corrective actions. AI must not present inference as accounting fact, generate EAC forecasts, or commit the program to recovery.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real EVM data is Employer-approved and routes only to an Employer-approved AI tool with explicit scope approval.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only when both the EVM data and the tool have explicit approval.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real EVM narrative.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Finance, EVM, and project accounting outputs.

## 4. Safe input requirements

Mirror W-06 §5:

- Synthetic EVM dataset (BCWS, BCWP, ACWP, CV, SV, CPI, SPI, EAC, ETC) for a fictional project.
- Generic CPI/SPI examples and fictional variance drivers.
- Tom's own notes from public EVM training.
- Generic corrective-action patterns from public PMI material.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-06 §6:

- Real EVM datasets, real cost or schedule values from employer systems.
- Real contract value, fee structure, or customer-funded categories.
- Real cause attribution to people, teams, vendors, or customers.

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[SYNTHETIC_PERIOD]` — fictional reporting period.
- `[APPROVED_INPUT]` — the EVM snapshot block (period and cumulative BCWS, BCWP, ACWP, CV, SV, CPI, SPI, EAC, ETC; WBS-level if available).
- `[PLACEHOLDER_OWNER]` — fictional WBS or corrective-action owner names.
- `[FICTIONAL_VARIANCE]` — the headline variance figure (e.g., "CPI=0.92, SPI=0.87").

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional draft an EVM variance explanation.

ROLE
- Structure the EVM snapshot into a cause-impact-corrective-action narrative.
- Frame apparent causes as observations of what the data and schedule show.
- Do not name causes not supported by the data.
- Do not invent corrective actions.
- Do not present AI inference as accounting fact.
- Do not generate EAC forecasts beyond what the formula produces from the inputs.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Period: [SYNTHETIC_PERIOD]
- Headline variance: [FICTIONAL_VARIANCE]
- EVM snapshot (period and cumulative; include WBS where present):
[APPROVED_INPUT]
- Known WBS / corrective-action owners: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown narrative with these sections, in this order:

1. **Metrics snapshot** — small Markdown table with rows for period and cumulative, columns for BCWS, BCWP, ACWP, CV, SV, CPI, SPI, EAC. Show units. Label period vs cumulative explicitly.
2. **What the metrics show** — 2-4 bullets, plain-language description of what the numbers say. No causes yet. No corrective actions yet.
3. **Cause (observed, not asserted)** — 1-3 bullets framing apparent drivers as observations of what the data and the schedule show. Attribute any real cause only to a named accountable owner from the inputs.
4. **Impact** — 1-2 bullets on the implications (EAC pressure, schedule pressure, customer-visible impact). Do not exaggerate; do not minimize.
5. **Corrective action** — 1-3 bullets naming a real, owned activity. If no corrective action exists in the inputs, write "no corrective action yet identified; decision pending [owner]."
6. **Open items / decisions needed** — 0-3 bullets.

DISCIPLINE
- Recompute CV = BCWP − ACWP. Recompute SV = BCWP − BCWS. Recompute CPI = BCWP / ACWP. Recompute SPI = BCWP / BCWS. If a number does not match the input, flag it as "recompute mismatch" in the snapshot table footnote and use the recomputed value.
- Label all forward-looking statements as forward-looking.
- Do not compare period CPI to cumulative SPI; keep units and periods aligned.
- Replace asserted causes ("Team Y underperformed") with observations ("BCWP is N% below BCWS for activities in WBS X; schedule shows starts later than planned").
- Append a "Number trace" list: each metric in the snapshot table mapped back to the input value or recomputed formula.

Return the narrative and the number trace only.
```

## 8. Expected output

A Markdown narrative with six labeled sections plus a small metrics snapshot table, followed by a "Number trace" list. Total body roughly 250-400 words. Mirrors W-06 §7.

## 9. Human review checklist

The reviewer (Tom; finance or program controls lead, and program manager for employer-deployable runs) follows the "Finance, EVM, and project accounting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before using the output:

- Recompute the key numbers (CV, SV, CPI, SPI, EAC, ETC) against source data.
- Confirm units and periods match.
- Confirm narrative does not state causes the data does not justify.
- Confirm the output does not present AI inference as accounting fact.
- Confirm corrective actions name real activities and real owners.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-06 §13):

- AI presents inference as accounting fact.
- Numbers do not recompute against the snapshot.
- Corrective actions are AI-generated rather than program-owned.
- Variance smoothed by selective period comparison.
- Reviewer signs off without recomputing.

Escalation triggers:

- The real cause involves contract, customer, or compliance matters — go to program lead and finance lead.
- EAC pressure exceeds approved tolerance — go to finance lead.
- The data turns out to span Prohibited content (customer fee structure, contract details) — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic EVM dataset, Personal AI tool, Standard review, sign-off line. Tom drafts; finance and program controls are accountable.
- **Employer-deployable form (after approval):** Real EVM data, Employer-approved AI tool against approved scope, Strict review (recompute every metric; remove every inferred cause), accountable owner is program manager and finance lead, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," stored in approved venue.
- **Re-approval triggers:** Broadening scope from variance explanation to forecast modeling; including contract-value detail; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm the EVM snapshot contains only synthetic values for personal-preparation runs.
- Confirm no WBS code or activity reference maps to a real employer program.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before sign-off. Required for Strict review intensity.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-06-evm-variance-explanation.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0018.
- Related artifact: A-0054 Synthetic EVM Workbook (Phase 9).
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-05-schedule-variance-narrative.md`, `P-09-accounting-reconciliation-narrative.md`.
