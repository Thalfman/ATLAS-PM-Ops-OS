# W-13-cross-tool-mismatch-investigation - Cross-tool data mismatch investigation

## Workflow identity

- **ID:** W-13
- **Backlog ID:** A-0037
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Cross-tool data mismatch investigation.

## 2. PM/Ops problem addressed

Status, schedule, and accounting views are produced by different tools (Microsoft Project, an accounting system, an action tracker, status documents) and frequently disagree because of timing, scope, or definitional differences. Without a structured investigation, the team argues about which tool is "right" instead of identifying the actual mismatch and resolving it.

## 3. Intended outcome

A short investigation record that names the mismatch precisely, identifies the candidate sources (timing, scope, definition, data entry), walks the verification path, and names the owner of each tool view. The output is a question list and a verification plan, not a verdict on which tool is correct.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real cross-tool data is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for the cross-tool content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real investigation.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Schedule outputs (for schedule-tool mismatches) and Finance, EVM, and project accounting outputs (for accounting-tool mismatches). Cite both as applicable.

## 5. Safe inputs

- Synthetic snapshots of two or more views (schedule, status, accounting, action tracker) for the same fictional period and scope.
- Generic mismatch examples from public PMI or audit material.
- Tom's own notes from public project-controls training.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real exports from employer schedule, accounting, status, or action systems without explicit approval.
- Real program structure, real owners, or real financial detail.
- Cross-tool data that reveals customer or contract relationships.

## 7. Output format

A two-part Markdown output:

**Part 1 - Mismatch table**

| # | Item or activity | Tool A view | Tool B view | Difference | Candidate cause (timing / scope / definition / data entry) | Verification step | Owner |
|---|---|---|---|---|---|---|---|

**Part 2 - Investigation plan**

- Verification path - ordered list of who to ask and what to check.
- Tool-view ownership - one line per view naming the owner.
- Definitional notes - one line per view describing what that view counts (period end, accrual, charged, planned, etc.).
- Decision needed - what the program needs to decide once the verification is complete.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic cross-tool snapshots. Same workflow runs unchanged in an Employer-approved AI tool against approved cross-tool data; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. Each tool view has its own accountable owner (scheduler, finance lead, action-tracker owner, status author); the investigation is owned by Tom or the program controls lead, but no view is declared "right" without its owner. Review intensity from §4 applies. Reviewer follows the applicable per-domain patterns in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: recompute numeric claims, confirm definitions and periods match, do not assign blame or make accounting determinations.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide two or more views.** Paste each tool view as a structured snapshot, with definitional notes (what the view counts).
4. **Ask AI to identify mismatches.** Prompt the AI to produce the §7 mismatch table. Forbid the AI from declaring a view correct.
5. **Ask AI to propose candidate causes.** Each candidate cause is one of: timing (different period boundaries), scope (different work content counted), definition (different counting rules), data entry (typos, swaps, lags). AI proposes; Tom and the view owners confirm.
6. **Build the verification path.** For each mismatch, name who to ask and what to check. Verification is sequential where dependencies exist.
7. **Tool-view owners confirm.** Each owner confirms their view's definition and the candidate cause for any mismatch affecting their view.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every mismatch shows both views' values and the difference.
- Candidate cause is one of the four named buckets, not a free-form guess.
- Verification step is concrete (who to ask, what to check).
- Owners are named for every view.
- Definitional notes explain why two correct-looking views can disagree.

Red flags:
- A mismatch row that declares one tool right.
- A candidate cause outside the four buckets without a stated reason.
- A verification step that says "look into it" without specifics.
- Definitional notes missing for a view that uses a non-standard definition.
- Sensitive program detail (real customer names, contract structure) inside the table.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": all tool snapshots, tool used, operator, reviewers (each view owner), accountable owner (program controls lead), date, outcome (which mismatches resolved), storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI declares a tool view incorrect without owner confirmation.
- Candidate causes are guesses outside the four buckets.
- Verification path lacks named owners.
- Definitional differences misattributed to data-entry errors (or vice versa).
- Reviewer accepts the table without engaging the view owners.

Escalation triggers (stop iterating the AI draft, go to a human):
- Mismatch indicates a real accounting or contract issue - go to finance lead.
- Mismatch indicates a real schedule integrity issue - go to scheduler and program lead.
- A view turns out to contain Prohibited content - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic cross-tool snapshots, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real cross-tool data, Employer-approved AI tool against approved scope, Strict review, owner confirmation per view, full audit envelope, stored in approved venue.
- **Re-approval triggers:** Broadening scope from mismatch identification to corrective accounting or schedule action; including customer-facing or contract-bearing views; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0037.
- Paired Phase 5 prompt: none. This workflow is investigative (mismatch identification and verification orchestration, not drafting); AI's role is to propose candidate causes, so no dedicated prompt is needed in the Phase 5 prompt library (A-0018, A-0019, A-0039..A-0047).
- Related demo: A-0051 Synthetic Discrepancy Triage Demo (Phase 7).
- Related workflows: W-04 (schedule health), W-05 (schedule variance), W-06 (EVM variance), W-08 (issue triage), W-09 (accounting reconciliation).
