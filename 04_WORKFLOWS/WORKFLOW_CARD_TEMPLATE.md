# WORKFLOW_CARD_TEMPLATE.md

Reusable template for every ATLAS workflow card. Copy this file to `04_WORKFLOWS/W-NN-<slug>.md`, replace bracketed placeholders, and append a row to the index in `WORKFLOW_LIBRARY.md`. Do not redefine governance language; cite the Phase 3 bundle by filename and section.

The 16 sections below cover the 12 required fields from the Phase 4 prompt plus the 4 governance citations from the Phase 3 bundle (D-0023 and D-0024) plus identity and cross-references.

---

# W-NN-<slug> - <Workflow Name>

## Workflow identity

- **ID:** W-NN
- **Backlog ID:** A-NNNN
- **Status:** Drafting | Ready for personal use | Deferred
- **Last updated:** YYYY-MM-DD

## 1. Workflow name

[One short line.]

## 2. PM/Ops problem addressed

[One short paragraph. Name the failure mode this workflow prevents.]

## 3. Intended outcome

[One short paragraph. State what "good" looks like after the workflow runs.]

## 4. Governance envelope

Cite the Phase 3 bundle by filename and section. Do not re-define these.

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): [Synthetic | Public | Tom-personal | Employer-approved | Prohibited]
- **Tool environment** (same file, "Tool environments"): [ATLAS-local Markdown | Personal AI tool | Employer-approved AI tool | No AI tool]
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): [Light | Standard | Strict]
- **Per-domain review pattern** (same file, "Per-domain review patterns"): [Status and reporting | Schedule | Finance, EVM, and project accounting | Meeting notes to action items | Risk and issue triage | SOP and lessons-learned]

If two categories or environments seem to apply, take the more restrictive one (per `DATA_SENSITIVITY_DECISION_MODEL.md`).

## 5. Safe inputs

- [Bullet list. Only synthetic, public, or Tom-personal inputs unless §4 routes to an employer-approved tool.]

## 6. Prohibited inputs

- [Bullet list. At minimum: classified, CUI, ITAR or export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting notes, real Microsoft Project files, real accounting exports - unless §4 explicitly routes to an employer-approved tool for an approved data scope.]

## 7. Output format

[Concrete shape: section headings, table columns, narrative length. Match what Tom would actually paste into a report or doc.]

## 8. Tool assumption

Gemini-first and platform-agnostic. [One line on the default tool environment and the migration target. Cross-reference §4.]

## 9. Human-in-the-loop review point

Named human reviewer: Tom (and, where relevant, the accountable owner - schedule owner, finance reviewer, risk owner, process owner). Review intensity from §4 applies. Reviewer follows the matching per-domain pattern from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. [Workflow-specific step. Verb-led, observable.]
4. [...]
5. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
6. **Record sign-off.** Per the review intensity recording rule in the same file.

## 11. Quality checks

Good output:
- [3-5 bullets. Concrete, observable.]

Red flags:
- [3-5 bullets. Things that mean the output is not ready to use.]

## 12. Audit and logging notes

For ATLAS personal preparation, the audit trail is the repo's commit history plus the relevant entry in `09_HANDOFFS/SESSION_HANDOFF.md`. For any employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums":

- Source of input.
- Tool used and environment.
- Operator (Tom).
- Reviewer and accountable owner.
- Date.
- Outcome (approved | edited | rejected).
- Storage location.

## 13. Failure modes and escalation triggers

Failure modes:
- [3-5 named failure modes specific to this workflow.]

Escalation triggers (when to stop iterating the AI draft and go to a human):
- [3-5 bullets.]

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** [How the workflow runs in ATLAS-local Markdown or Personal AI tool with synthetic or Tom-personal inputs.]
- **Employer-deployable form (after approval):** [What changes when the workflow runs against Employer-approved data in an Employer-approved AI tool: audit-trail uplift, accountable owner, where the output is stored.]
- **Re-approval triggers:** [Any change that requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.]

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-NNNN.
- Paired Phase 5 prompt (if any): `05_PROMPTS/...` (TBD until Phase 5).
- Related workflows: [W-NN, W-NN].
