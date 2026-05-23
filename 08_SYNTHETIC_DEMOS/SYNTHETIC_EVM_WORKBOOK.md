# SYNTHETIC_EVM_WORKBOOK.md

**SYNTHETIC WORKBOOK. FICTIONAL EVM NUMBERS. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0054
- **Phase:** 9 - EVM, Finance, and Project Accounting Track
- **Shared scenario:** `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`
- **Pack index:** `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`
- **Paired workflow card:** `04_WORKFLOWS/W-06-evm-variance-explanation.md`
- **Paired prompt card:** `05_PROMPTS/P-06-evm-variance-explanation.md`
- **Sibling Phase 8 substrate:** `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A fictional EVM dataset (BCWS, BCWP, ACWP, CV, SV, CPI, SPI, EAC, ETC) for Project Northstar Demo at the week-3 cutoff. The workbook exists so EVM variance prompts and demos have a defensible synthetic substrate. Numbers are round, generic, and obviously fictional; no currency commitment, no real cost-account structure, no real EAC formulas tied to a real contract.

## Governance envelope

- **Data category:** Synthetic.
- **Tool environment:** ATLAS-local Markdown; Personal AI tool acceptable for the AI-step exercises against this workbook because the input is Synthetic.
- **Review intensity:** Light for personal practice.
- **Per-domain review pattern:** Finance, EVM, and project accounting outputs (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`).

Full citation pattern inherited from `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.

## EVM terminology (synthetic-practice definitions)

These follow public PMI definitions. Real-program terminology and thresholds may differ; the reviewer never asserts employer-specific definitions.

- **BCWS** Budgeted Cost of Work Scheduled (planned value).
- **BCWP** Budgeted Cost of Work Performed (earned value).
- **ACWP** Actual Cost of Work Performed.
- **CV** Cost Variance = BCWP − ACWP. Negative is overrun.
- **SV** Schedule Variance = BCWP − BCWS. Negative is behind schedule.
- **CPI** Cost Performance Index = BCWP / ACWP. <1 is overrun.
- **SPI** Schedule Performance Index = BCWP / BCWS. <1 is behind.
- **BAC** Budget at Completion.
- **EAC** Estimate at Completion. Multiple formulas exist; the workbook uses EAC = BAC / CPI as the canonical illustrative formula and notes when alternative formulas would change the result.
- **ETC** Estimate to Complete = EAC − ACWP.

Numbers below are illustrative round units (no currency). They look obviously synthetic.

## Synthetic control-account structure

Three control accounts mirror the workstreams from the shared scenario.

| CA ID | Control account | Owner | BAC |
|---|---|---|---:|
| CA-A | Reporting | Workstream A Lead | 400 |
| CA-B | Action tracking | Workstream B Lead | 300 |
| CA-C | Risk and decision capture | Workstream C Lead | 200 |
| (Total) | Project Northstar Demo | PM/Ops | 900 |

## Workbook at week-3 cutoff (2026-05-22)

| CA | BCWS | BCWP | ACWP | CV | SV | CPI | SPI |
|---|---:|---:|---:|---:|---:|---:|---:|
| CA-A | 200 | 180 | 200 | -20 | -20 | 0.90 | 0.90 |
| CA-B | 150 | 120 | 140 | -20 | -30 | 0.86 | 0.80 |
| CA-C | 100 | 100 | 95 | +5 | 0 | 1.05 | 1.00 |
| Total | 450 | 400 | 435 | -35 | -50 | 0.92 | 0.89 |

Project-level EAC (illustrative, using EAC = BAC / CPI): 900 / 0.92 = ~978. ETC = 978 − 435 = ~543. Alternative formulas (EAC = ACWP + (BAC − BCWP), EAC = ACWP + (BAC − BCWP) / (CPI × SPI)) would give different results; reviewer chooses the formula consistent with the program's reporting practice.

## Synthetic narrative observations (illustrative, not asserted)

- **CA-A Reporting:** Both CV and SV negative by 20 units; CPI / SPI both 0.90. Observation: schedule and cost moved together, consistent with a delivery slip rather than a labor-rate or material issue. Cross-references the Phase 7 schedule variance demo (NS-A-03 +4 days finish).
- **CA-B Action tracking:** Deepest CPI dip (0.86), SPI 0.80. Schedule slipping faster than cost is being earned. Observation: tracker buildout took longer than planned (Phase 7 NS-B-01 +2 days, NS-B-02 +4 days); cost slightly elevated.
- **CA-C Risk and decision capture:** Positive CV (+5) and zero SV. Observation: on track and slightly under cost; risk-review workshop closed on schedule.

## Synthetic variance driver categories (PMI-style)

Drivers are categories AI may propose; the reviewer decides which apply.

- **Schedule-driven cost variance:** activity took longer; labor accrued; earned value lagged.
- **Estimate accuracy:** original BCWS underestimated effort; revisit baseline.
- **Productivity:** team encountered learning curve or rework.
- **Material / vendor:** material or vendor cost differed from plan. (Not applicable to this scenario — Project Northstar Demo is process-improvement work without procurement.)
- **Scope creep:** undocumented scope added without re-baseline.
- **Reporting cutoff timing:** ACWP captured before BCWP fully posted, or vice versa.

For this synthetic snapshot, CA-A's drivers most plausibly are "schedule-driven cost variance" (NS-A-03 +4 days propagation) and CA-B's drivers most plausibly are "estimate accuracy" (tracker buildout effort underestimated) plus "schedule-driven cost variance" (owner-confirmation dependency). Reviewer confirms; AI proposes, does not assert.

## EVM cutoff and data-date awareness

- The workbook is a snapshot at status date 2026-05-22.
- BCWS reflects planned value through the cutoff; BCWP and ACWP reflect work completed and cost incurred through the same cutoff.
- A mismatch in cutoff (e.g., BCWP through 2026-05-22 vs ACWP through 2026-05-19) would produce a false CV. The reviewer confirms cutoff alignment before drawing variance conclusions.

## Things AI must not do with this workbook

- AI never asserts a financial root cause as fact ("The team is over budget because of X"). AI proposes driver candidates as observations.
- AI never sets or changes BAC, BCWS, BCWP, ACWP. Those are owner / control-account-manager decisions.
- AI never picks an EAC formula on its own. Reviewer chooses based on program practice.
- AI never certifies EVM status. The reviewer and the EVM analyst do.
- AI never produces a narrative against real EVM data inside a personal AI tool. Real EVM data flows only through an Employer-approved AI tool after re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## How to use this workbook

1. **With `W-06` / `P-06`:** feed the workbook table into P-06 (placeholders filled with `[SYNTHETIC_PROJECT_NAME]` = Project Northstar Demo, `[SYNTHETIC_PERIOD]` = 2026-05-04 through 2026-05-22) to draft an EVM variance narrative. AI proposes driver candidates; reviewer confirms.
2. **With the Phase 8 schedule workbook:** cross-walk CA-A and CA-B variances against the schedule slips (NS-A-03 critical path, NS-B-01 → NS-B-02 propagation) to verify the schedule-driven cost variance hypothesis.
3. **As a synthetic-demo backdrop in conversations:** walk through one control account at a time; show how the AI structures driver candidates rather than asserting them.

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-06-evm-variance-explanation.md`.
- Paired prompt card: `05_PROMPTS/P-06-evm-variance-explanation.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Phase 8 schedule substrate: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`.
- Phase 8 health template (analogous shape on the schedule side): `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`.
- Sibling Phase 9 demo: `08_SYNTHETIC_DEMOS/SYNTHETIC_ACCOUNTING_RECONCILIATION_DEMO.md`.
- Sibling Phase 9 workflow: `04_WORKFLOWS/W-17-accounting-discrepancy-triage.md`.
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0054.
- Decision log: D-0052..D-0054 (Phase 9 set).
