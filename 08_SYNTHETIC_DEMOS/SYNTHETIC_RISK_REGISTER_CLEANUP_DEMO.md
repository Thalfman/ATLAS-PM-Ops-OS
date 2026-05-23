# SYNTHETIC_RISK_REGISTER_CLEANUP_DEMO.md

**SYNTHETIC DEMO. FICTIONAL RISK REGISTER. NOT MOTOROLA SOLUTIONS, NOT ANY REAL PROGRAM, CUSTOMER, OR CONTRACT.**

## Artifact identity

- **Backlog ID:** A-0052
- **Phase:** 7 - Synthetic Demo Pack
- **Paired workflow card:** `04_WORKFLOWS/W-07-risk-register-cleanup.md`
- **Paired prompt card:** `05_PROMPTS/P-07-risk-register-cleanup.md`
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

Walk a risk-register cleanup end-to-end: a fictional pre-cleanup register on Project Northstar Demo with the usual hygiene problems (vague entries, duplicates, missing triggers, weak ownership), an AI-drafting step using P-07 that produces a cleaned register and a hygiene-notes list, and a human-review pass where risk owners sign off before the cleaned register replaces the original.

## Step 1 - Synthetic input (pre-cleanup register)

Seven entries. Each row is deliberately rough.

| # | Risk wording | Owner | Probability | Impact | Mitigation | Status |
|---|---|---|---|---|---|---|
| 1 | Schedule risk. | TBD | Med | High | "Watch schedule." | Open |
| 2 | If action owners are not confirmed during meetings, follow-up may be delayed and status quality may decline. | PM/Ops | High | Med | Require owner/date confirmation before meeting close. | Open |
| 3 | Reporting risk. | PM/Ops | Med | Med | "Improve reporting." | Open |
| 4 | Owner availability risk on action tracker rollout. | Team Lead | Med | Med | "Get owners in the room." | Open |
| 5 | Decision capture risk — decisions are not being recorded consistently. | TBD | Med | Med | "Add decision log." | Open |
| 6 | If the weekly status template is too complex, adoption may be inconsistent. | PM/Ops | Med | Low | Keep format to one page; review after two cycles. | Open |
| 7 | Risk of pilot feedback being insufficient to feed lessons-learned. | TBD | Low | Med | "Get more feedback." | Open |

Pre-cleanup observations:

- Rows 1 and 3 are not conditioned (they are categories, not risks).
- Rows 2 and 4 may overlap (both involve owner discipline).
- Rows 5 and 6 are well-formed; row 6 condition-consequence is intact.
- Rows 1, 5, 7 have TBD owners.
- Several mitigations are vague ("Watch schedule.", "Improve reporting.", "Get more feedback.").

## Step 2 - AI step (P-07 invocation pattern)

Tom runs `P-00-safety-precheck.md`: Synthetic, Personal AI tool, Tom as reviewer, paired W-07. Clear.

Tom sends the register through P-07 with placeholders filled. P-07 forbids AI from assigning probability/impact, deciding response strategy, or merging without flagging — AI proposes; risk owners decide.

## Step 3 - AI cleaned register (before review)

| # | Condition | Consequence | Trigger | Owner | Probability | Impact | Response (avoid / mitigate / transfer / accept) | Response status | Notes |
|---|---|---|---|---|---|---|---|---|---|
| 1 | (Original "Schedule risk" — AI proposes retirement; not conditioned, no clear trigger.) | — | — | TBD | (carried) Med | (carried) High | — | Retire candidate | AI cannot rewrite into condition-consequence without invention; flags for owner decision. |
| 2 | If action owners are not confirmed during meetings, | follow-up may be delayed and status quality may decline. | More than 20% of actions have TBD owners at meeting close. | PM/Ops | (carried) High | (carried) Med | Mitigate | Active | Mitigation: require owner/date confirmation before meeting close. Cross-reference: action A-105 implements this. |
| 3 | (Original "Reporting risk" — AI proposes retirement; not conditioned.) | — | — | PM/Ops | (carried) Med | (carried) Med | — | Retire candidate | Not a usable risk statement; flag for owner decision or rewrite. |
| 4 | If owner availability for the action tracker rollout slips, | the rollout date may extend beyond the M-02 milestone. | Owner availability conflicts identified in the prior week. | Team Lead | (carried) Med | (carried) Med | Mitigate | Active | AI notes possible overlap with row 2 — both involve owner discipline at different stages (meeting close vs. rollout planning). Owner decides whether to merge. |
| 5 | If decisions are not captured consistently in meeting notes, | rework and misalignment may increase across workstreams. | More than one decision per meeting goes unrecorded. | TBD | (carried) Med | (carried) Med | Mitigate | Active | Mitigation: add decision-log section to meeting template. AI proposes Team Lead as owner candidate; risk owner decides. |
| 6 | If the weekly status template is too complex, | adoption may be inconsistent across workstreams. | Users skip sections or create parallel formats. | PM/Ops | (carried) Med | (carried) Low | Mitigate | Active | Mitigation: keep format to one page; review after two cycles. Already well-formed in the original register. |
| 7 | If pilot feedback is insufficient to characterize the operating-rhythm change, | lessons-learned first draft may be premature or generic. | Fewer than three usable feedback entries per pilot workstream. | TBD | (carried) Low | (carried) Med | Mitigate | Active | Mitigation: schedule a pilot retrospective on the project schedule. Cross-references the issue triage row 5. AI proposes Workstream B Lead as owner candidate. |

## Hygiene notes (AI draft, before review)

- **Retirement candidates:** Rows 1 and 3. Both are categories ("schedule risk," "reporting risk"), not conditioned risk statements. AI did not rewrite them into invented condition-consequence form; owner decides whether to retire or replace.
- **Possible duplicates / merge candidates:** Rows 2 and 4 both touch owner discipline. AI proposes that they stay separate because row 2 is about meeting-close practice and row 4 is about rollout planning; risk owners decide.
- **Missing fields:** Rows 1, 5, 7 had TBD owners. AI did not invent owners. For row 5 and 7, AI proposes owner candidates (Team Lead, Workstream B Lead) based on workstream alignment in `SYNTHETIC_PROJECT_SCENARIO.md`; owner assignment is the human's call.
- **Themes:** Three entries (rows 2, 4, 5) are about operating-rhythm discipline (owner confirmation, decision capture). They could be summarized as a single theme in the readout without merging the risk entries themselves.

## Step 4 - Human review (Risk and issue triage outputs pattern)

Per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Risk and issue triage outputs":

- **Every entry has an owner?** Rows 1, 5, 7 still missing. Tom (or the named risk owners during the synthetic risk-review workshop) assign: row 1 → retire, row 5 → Team Lead, row 7 → Workstream B Lead.
- **Categorization matches judgment?** Probability and impact carried over from the pre-cleanup register; in a real review the owners revisit each. For this demo Tom leaves them as-is and flags them for the workshop.
- **Mitigation actionable?** Yes for rows 2, 4, 5, 6, 7 after cleanup. Rows 1 and 3 retired.

## Step 5 - Final register (after review)

| # | Condition | Consequence | Trigger | Owner | Probability | Impact | Response | Status |
|---|---|---|---|---|---|---|---|---|
| 2 | If action owners are not confirmed during meetings, | follow-up may be delayed and status quality may decline. | >20% of actions have TBD owners at meeting close. | PM/Ops | High | Med | Mitigate (owner/date confirmation at meeting close) | Active |
| 4 | If owner availability for the action tracker rollout slips, | rollout date may extend beyond M-02. | Owner availability conflicts identified in the prior week. | Team Lead | Med | Med | Mitigate (advance owner scheduling) | Active |
| 5 | If decisions are not captured consistently in meeting notes, | rework and misalignment may increase. | >1 decision per meeting goes unrecorded. | Team Lead | Med | Med | Mitigate (decision-log section in meeting template) | Active |
| 6 | If the weekly status template is too complex, | adoption may be inconsistent. | Users skip sections or create parallel formats. | PM/Ops | Med | Low | Mitigate (one-page format; review after two cycles) | Active |
| 7 | If pilot feedback is insufficient to characterize the operating-rhythm change, | lessons-learned first draft may be premature. | <3 usable feedback entries per pilot workstream. | Workstream B Lead | Low | Med | Mitigate (schedule pilot retrospective) | Active |

Rows 1 and 3 retired (not conditioned, no actionable rewrite without invention).

```text
Reviewer sign-off: Tom (Light intensity, synthetic input), 2026-05-23.
Risk owners to confirm probability and impact at the synthetic risk-review workshop on 2026-05-20.
```

## Demo value

The AI does the structuring work (rewriting condition-consequence statements where the source supports it, flagging non-conditioned entries, surfacing duplicates and missing fields, proposing owner candidates by workstream alignment) but does not invent. Probability, impact, response strategy, and final ownership remain human decisions. The pattern carries forward to real risk registers only inside an Employer-approved AI tool with explicit scope approval per W-07 §14.

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-07-risk-register-cleanup.md`.
- Paired prompt card: `05_PROMPTS/P-07-risk-register-cleanup.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Shared scenario: `08_SYNTHETIC_DEMOS/SYNTHETIC_PROJECT_SCENARIO.md`.
- Cross-demo references: `08_SYNTHETIC_DEMOS/SYNTHETIC_ACTION_TRACKER_DEMO.md` (action A-105 implements R-002 mitigation); `08_SYNTHETIC_DEMOS/SYNTHETIC_DISCREPANCY_TRIAGE_DEMO.md` (row 4 R-001 cross-reference, row 5 pilot retrospective).
- Pack index: `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0052.
