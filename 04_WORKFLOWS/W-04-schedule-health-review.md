# W-04-schedule-health-review - Microsoft Project schedule health review

## Workflow identity

- **ID:** W-04
- **Backlog ID:** A-0015 (Phase 8 - Microsoft Project and Schedule Integrity Track)
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Microsoft Project schedule health review (synthetic or approved data only).

## 2. PM/Ops problem addressed

Schedules accumulate hygiene problems quietly: missing predecessors, broken or dangling logic, stale dates, unbaselined activities, hard constraints replacing logic, summary-level work without children. A reviewer without a checklist either misses these or argues with the scheduler about technical estimates instead of structural integrity. The PM/Ops role is to surface structural hygiene, not to redo the estimating work.

## 3. Intended outcome

A short observation list that names the structural schedule hygiene issues in a snapshot, framed as questions for the scheduler and SMEs rather than verdicts. Tom owns surfacing the questions; the scheduler and SMEs own the answers and the estimates.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real schedule data is Employer-approved at best and routes only to an Employer-approved AI tool with explicit scope approval.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only when both the schedule and the tool have explicit approval for this use case.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real schedule (which only happens in approved employer environments).
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Schedule outputs.

## 5. Safe inputs

- Synthetic task list, fictional dependencies, generic schedule fields (activity ID, name, predecessor, successor, duration, start, finish, baseline, total float).
- Generic schedule-hygiene checklists from public PMI material.
- Tom's own notes from public scheduling training.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real `.mpp` files from any employer system.
- Real activity IDs, real WBS names, or real program identifiers.
- Real customer, contract, or financial linkages inside the schedule.
- Paraphrased or screenshot content from a restricted schedule.

## 7. Output format

A two-part Markdown output:

**Part 1 - Hygiene observation list**

| # | Activity ID | Observation | Severity (info / warn / blocker) | Per-row question for scheduler/SME |
|---|---|---|---|---|

**Part 2 - Summary**

- Total activities reviewed.
- Counts by severity.
- 3-5 themes (e.g., "missing predecessors on testing path," "hard constraints replacing logic").
- 3-5 questions to bring to the scheduler / SMEs.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with a synthetic schedule. The same workflow runs unchanged in an Employer-approved AI tool against an approved real schedule; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. The accountable owner for any technical estimate or recovery date is the scheduler or the activity owner; Tom surfaces questions but does not override technical judgment. Review intensity from §4 applies. Reviewer follows the "Schedule outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: recompute or sanity-check numeric claims, confirm narrative matches underlying data, confirm activity names and IDs match the source, do not over-attribute causes or commit to recovery dates the schedule does not support.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide a schedule snapshot.** Export or paste the schedule as a structured table (activity ID, name, predecessor, successor, duration, start, finish, baseline, total float).
4. **Ask AI to flag hygiene only.** Prompt the AI to identify missing predecessors, dangling activities, hard constraints, stale baselines, summary work without children, total-float anomalies, and naming or ID inconsistencies. Forbid the AI from estimating, re-baselining, or recommending dates.
5. **Verify each observation against the snapshot.** Open the activity ID; confirm the issue is real. Edit or drop observations the data does not support.
6. **Frame each observation as a question.** Convert "missing predecessor" into "what activity should precede 1234, or is the start condition external?"
7. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
8. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every observation traces to a specific activity ID in the snapshot.
- Observations are structural (logic, baseline, constraint), not estimating.
- Questions, not verdicts.
- Severity is supported by stated criteria.
- Themes are short and would be useful to a scheduler reviewing the list cold.

Red flags:
- "Recommended duration" or "recommended completion date" anywhere in the output.
- Observations that depend on data not in the snapshot.
- Numeric claims that do not match the snapshot when recomputed.
- AI-suggested replanning that touches scope or work content.
- Phrasing that blames the scheduler.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": schedule snapshot, tool, operator, reviewer (scheduler/SME), accountable owner (program), date, outcome (questions raised, observations resolved), storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI proposes durations or recovery dates the data does not justify.
- AI flags hygiene issues that do not exist in the snapshot.
- AI restructures the network instead of surfacing the question.
- Observation phrasing reads as a verdict on the scheduler.
- Reviewer accepts observations without opening the activity ID.

Escalation triggers (stop iterating the AI draft, go to a human):
- The schedule's underlying data is incomplete - go to the scheduler.
- Hygiene issues span multiple owners and need a coordinated decision - go to program management.
- The schedule turns out to be restricted under `DATA_SENSITIVITY_DECISION_MODEL.md` - stop, do not use AI.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic schedule, Personal AI tool, Standard review, sign-off line. Tom builds the question list; the scheduler is the accountable owner of any change.
- **Employer-deployable form (after approval):** Real schedule export from an approved venue, Employer-approved AI tool with approved scope, Strict review (recompute float, sanity-check baselines), accountable owner is the scheduler or program manager, full audit envelope.
- **Re-approval triggers:** Switching from observation-only to recommended-action output; broadening scope beyond hygiene to estimating; new tool environment; new data scope. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0015 (Phase 8 deliverable; this card is the Phase 4 workflow that pairs with it).
- Paired Phase 5 prompt: none. This workflow is structural (hygiene observation, not drafting); AI's role is to flag and question, so no dedicated prompt is needed in the Phase 5 prompt library (A-0018, A-0019, A-0039..A-0047).
- Related artifacts: A-0053 Synthetic Schedule Workbook (Phase 8).
- Related workflows: W-05 (schedule variance narrative), W-09 (accounting reconciliation), W-13 (cross-tool mismatch investigation).
