# W-08-issue-and-discrepancy-triage - Issue and discrepancy triage

## Workflow identity

- **ID:** W-08
- **Backlog ID:** A-0012
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Issue and discrepancy triage.

## 2. PM/Ops problem addressed

Issues and discrepancies arrive in many shapes (a customer email, an inconsistency between two reports, a missed milestone, a flagged audit finding) and frequently sit unresolved because they were never converted into a trackable resolution path. The team can describe the issue but not the next concrete step or its owner.

## 3. Intended outcome

A short triage record for each issue or discrepancy with: a one-line description, severity, the affected scope, the named owner, the next concrete step, the expected resolution date, and a status. Tom does the assigning; AI structures, names blind spots, and proposes investigation steps.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real issues are Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for issue content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Risk and issue triage outputs.

## 5. Safe inputs

- Synthetic issue or discrepancy notes for a fictional project.
- Generic issue examples from public PMI or quality-management material.
- Tom's own notes from a public training or his own non-restricted observations.

## 6. Prohibited inputs

- Real customer complaints, real audit findings, real contract disputes.
- Real personnel or performance issues.
- Issues that reveal restricted program structure, real systems, or financial impact.

## 7. Output format

A Markdown triage table:

| # | One-line description | Severity (S1-S4) | Affected scope | Owner | Next step | Target date | Status (open / in progress / blocked / closed) | Notes |
|---|---|---|---|---|---|---|---|---|

Plus, below the table:

- **Severity definitions** - one line each, e.g., S1 = stops work; S2 = degrades quality or schedule; S3 = inconveniences; S4 = informational.
- **Investigation candidates** - issues where the next step is "investigate" rather than "fix"; AI may suggest investigation questions but not conclusions.
- **Open ownership** - issues with no clear owner; Tom assigns before the triage record is used.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic input. Same workflow runs unchanged in an Employer-approved AI tool against approved issue content; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. For any issue with an external owner or external impact, the accountable owner is whoever owns the affected scope. Review intensity from §4 applies. Reviewer follows the "Risk and issue triage outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: confirm each entry has an owner, confirm severity matches judgment (not AI inference), confirm the next step is actionable.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide the raw issue list.** Paste issue or discrepancy descriptions in whatever form they arrived. Include source (email, report, observation) when not sensitive.
4. **Ask AI to convert to triage rows.** Prompt the AI to produce the §7 table. Forbid the AI from assigning severity or owner; those fields are populated by Tom or are labeled "missing."
5. **Ask AI to propose investigation questions.** For ambiguous issues, AI suggests 2-3 questions that would resolve the ambiguity. AI does not propose conclusions.
6. **Tom assigns severity and owner.** AI may suggest severity with a reason; Tom decides. AI may suggest an owner from the source; Tom confirms with the owner.
7. **Confirm next step with the owner.** Before the triage record is used for tracking, the named owner has agreed to the next step (or it remains in "open ownership" until they do).
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every row has a one-line description, affected scope, and a next step.
- Severity is assigned by Tom with a stated criterion.
- Owners are real, named, and confirmed.
- Investigation candidates are clearly separated from fix candidates.
- Notes column references the source of the issue.

Red flags:
- AI-assigned severity with no criterion.
- "Investigate" as a next step that has no investigation question behind it.
- An owner who has not agreed to the next step.
- A row that conflates two distinct issues.
- A closed status with no closing note.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": raw issue list, tool, operator, reviewer, accountable owner, date, outcome (severity assigned, owner confirmed, next step set), storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI assigns severity without criterion or merges two distinct issues.
- Next step is verb-only ("address it") with no concrete action.
- Owner is assigned without confirmation.
- Triage record diverges from the source list between iterations.
- Closed issues lose the audit trail of how they were closed.

Escalation triggers (stop iterating the AI draft, go to a human):
- Issue crosses into safety, compliance, contract, or customer-facing territory - go to program lead.
- Issue requires authority Tom does not have - go to manager.
- Issue turns out to involve Prohibited content - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic issue list, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real issue list, Employer-approved AI tool against approved scope, Strict review, owner-confirmation step before the triage record is used in any official tracker, full audit envelope.
- **Re-approval triggers:** Including customer-facing or contract-bearing issues; broadening scope to root-cause analysis; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0012.
- Paired Phase 5 prompt: A-0043 Issue and Discrepancy Triage Prompt (TBD in Phase 5).
- Related demo: A-0051 Synthetic Discrepancy Triage Demo (Phase 7).
- Related workflows: W-07 (risk register cleanup), W-13 (cross-tool mismatch).
