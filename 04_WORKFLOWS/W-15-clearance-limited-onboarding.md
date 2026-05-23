# W-15-clearance-limited-onboarding - Clearance-limited onboarding workflow

## Workflow identity

- **ID:** W-15
- **Backlog ID:** A-0068
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Clearance-limited onboarding workflow.

## 2. PM/Ops problem addressed

A new project controls or PM/Ops hire in a federal/defense-adjacent environment frequently waits weeks or months for clearance before they can touch real program content. Without a structured pattern, the wait becomes idle time and the hire arrives at the cleared workstream with little observable PM/Ops or AI value already demonstrated. The risk is double: missed momentum and a missed chance to position the role.

## 3. Intended outcome

A small set of personal-preparation activities Tom can run during clearance-limited onboarding to demonstrate observable PM/Ops and AI value without touching restricted content. Each activity is owned, scheduled, and produces an artifact a manager can see. The workflow makes it easy for Tom and the manager to agree on the week's commitments.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Tom-personal. Public when based on public material. Never Employer-approved while clearance is pending - that is the point.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown for all artifacts. Personal AI tool when Tom's own notes or public material are the input. No employer system access while clearance is pending.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Light by default for personal practice; Standard for any artifact shared with the manager.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## 5. Safe inputs

- Tom's own preparation notes, observations from public meetings, training notes.
- Public PMI, PMBOK, EVM, schedule-integrity, and project-controls material.
- Synthetic ATLAS content (demos, templates, workflows already in this repo).
- Public vendor documentation for approved-tool candidates.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Any restricted content overheard or observed in clearance-limited spaces.
- Paraphrased content from a restricted briefing Tom was permitted to observe.
- Real program names, customer names, contract IDs.
- Anything that would not be acceptable inside the personal-preparation boundary in `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.

## 7. Output format

A small weekly plan in Markdown with these sections:

1. **Week's commitments to manager** - 3-5 bullets, each verb-led, each with a visible artifact and target date.
2. **Daily activity pattern** - 3-5 lines naming the recurring practice (morning study, afternoon synthetic exercise, end-of-day listening log).
3. **Listening log** - structured place to record observed process gaps, reporting issues, or AI-adjacent pain points (without restricted content); pairs with W-16 process gap notes when those exist.
4. **Artifacts produced this week** - links or paths to the artifacts Tom built; each is a personal-preparation artifact (synthetic or Tom-personal).
5. **What to discuss with manager next** - 1-3 bullets framing the next conversation: scope clarifications, value Tom can offer, what unblocks Tom.

## 8. Tool assumption

ATLAS-local Markdown for the plan and the artifacts; Personal AI tool optionally for drafting and structuring. No employer-approved AI tool until clearance and policy allow it. Same workflow runs unchanged once clearance lands - the data category shifts, not the structure; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom for daily practice. Manager is the accountable approver for the weekly commitments and the "what I can offer this week" framing; Tom does not commit to scope beyond what he and the manager have agreed. Review intensity from §4 applies. Reviewer follows the "Status and reporting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: verify every claim has a source, mark forward-looking statements, do not overclaim.

## 10. Step-by-step process

1. **Classify the input.** Confirm all inputs are Tom-personal, Public, or Synthetic. Clearance-limited means no Employer-approved use. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Set the week's commitments.** Three to five concrete commitments. Each has a visible artifact (a written summary, a synthetic demo refinement, a study note, an SOP draft, a workflow card review) and a target date.
4. **Run the daily pattern.** Morning study from public PMI / EVM / schedule material; afternoon synthetic exercise using `08_SYNTHETIC_DEMOS/` content; end-of-day listening log entry.
5. **Maintain the listening log.** Capture observed process gaps and AI-adjacent pain points in neutral language. Do not include restricted content. Process gaps that warrant a note pair with W-16 (process gap note workflow) when that exists.
6. **Produce the artifacts.** Each artifact lands in ATLAS or in Tom's own notes. Artifacts demonstrate PM/Ops and AI value without touching restricted content.
7. **Review with manager.** End of week: review commitments delivered, share artifacts, propose the next week's commitments, ask the targeted unblock question.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Light intensity: one-line note in the weekly plan. Standard intensity (for the manager-shared "what I can offer" one-pager): sign-off line in the document.

## 11. Quality checks

Good output:
- Every commitment has a visible artifact.
- Daily pattern is sustainable - Tom can actually run it every day this week.
- Listening log entries are neutral and contain no restricted content.
- Artifacts are concrete (links or paths), not aspirational.
- The manager conversation is short and specific.

Red flags:
- Commitments that depend on cleared access Tom does not have yet.
- Listening log entries that paraphrase restricted content.
- Artifacts that overclaim value beyond what Tom could demonstrate.
- Weekly plan grows longer than the week's available time.
- "What I can offer" framing that exceeds the role Tom and the manager have agreed.

## 12. Audit and logging notes

The audit trail for clearance-limited work is this repo's commit history plus Tom's personal notes plus the weekly plan. No employer audit envelope applies - that is the point of clearance-limited mode. Personal-preparation artifacts stay personal until cleared and approved migration happens (Phase 11).

## 13. Failure modes and escalation triggers

Failure modes:
- Tom commits to scope outside what clearance allows.
- Listening log inadvertently captures restricted content.
- "What I can offer" framing overclaims expertise or scope.
- Weekly plan accumulates without delivery.
- Synthetic demos start to look like employer content (real-sounding names, dates).

Escalation triggers (stop iterating the AI draft, go to a human):
- A commitment requires clearance that has not landed - go to manager, restate scope.
- Listening log captured restricted content - delete the entry, do not retain, do not paraphrase.
- A potential value-add is genuinely strong but needs employer approval to test - hold the idea for the Phase 11 migration plan; do not silently scope it.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** All artifacts ATLAS-local Markdown or Tom-personal; manager-shared artifacts are concrete and observable; no employer data used.
- **Post-clearance form:** Same weekly-plan structure adapted to the actual cleared scope. Commitments now reference real program content; review intensity moves to Standard or Strict; artifacts live in the approved employer venue when applicable. The structure does not change; the data category and tool environment do.
- **Re-approval triggers:** Any artifact moving from personal preparation to employer-deployable per `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md` (D-0026); any AI use against employer content. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0068.
- Paired Phase 5 prompt: none. This workflow is personal-planning (weekly commitment shape, daily pattern, listening log structure, not drafting); AI's role is optional structuring, so no dedicated prompt is needed in the Phase 5 prompt library (A-0018, A-0019, A-0039..A-0047).
- Related Phase 6 artifacts: A-0022 Clearance-Limited Value Plan, A-0048 Listening Plan, A-0050 "What I Can Offer This Week" One-Pager, A-0049 Onboarding Question Set, A-0005 First-Week Discovery Script, A-0006 Executive Narrative Template.
- Related workflows: W-01 (weekly status report), W-12 (executive brief generation), and the future W-16 (process gap note, A-0038) when that is built.
