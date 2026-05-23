# W-05-schedule-variance-narrative - Schedule variance narrative drafting

## Workflow identity

- **ID:** W-05
- **Backlog ID:** A-0016 (Phase 8 - Microsoft Project and Schedule Integrity Track)
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Schedule variance narrative drafting.

## 2. PM/Ops problem addressed

Schedule variance gets reported as a number (days slipped, percent complete) without a narrative explaining what moved, why it moved, and what the recovery posture is. Or, the narrative overclaims (asserts causes the data does not support) or under-claims (smooths the variance out of leadership view). Both failure modes erode trust in the reporting.

## 3. Intended outcome

A short variance narrative grounded in the schedule delta: what variance is present, what activities or paths drive it, what the apparent (not asserted) cause is, what the recovery posture looks like, and what decision or input the project needs. Numbers traceable, causes stated as observations not conclusions.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real schedule deltas are Employer-approved and route only to an Employer-approved AI tool with explicit scope approval.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only when both the variance data and the tool have explicit approval.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real variance narrative.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Schedule outputs.

## 5. Safe inputs

- Synthetic schedule delta showing baseline vs current dates for a fictional project.
- Generic variance examples from public PMI material.
- Tom's own notes from public schedule-analysis training.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real schedule deltas from any employer system without explicit approval.
- Real activity names, IDs, baselines, or owner attribution.
- Restricted causal explanations (customer behavior, contract changes, real technical issues).

## 7. Output format

A short Markdown narrative with these sections:

1. **Variance summary** - one paragraph with the headline numbers (days slipped, paths affected).
2. **What moved** - 3-5 bullets, each citing activity ID and the magnitude of the move.
3. **Apparent cause** - 1-3 bullets, framed as observations ("schedule shows X starting N days after planned start") not conclusions ("Team Y delayed").
4. **Recovery posture** - 1-3 bullets on what the schedule shows planned for recovery; named owner.
5. **Decisions or inputs needed** - 0-3 bullets.

Total length: roughly 250-400 words.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with a synthetic delta. The same workflow runs unchanged in an Employer-approved AI tool against an approved real variance; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. The accountable owner for the narrative content is the scheduler and the program lead. Review intensity from §4 applies. Reviewer follows the "Schedule outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: recompute or sanity-check variance percentages and durations, confirm narrative matches underlying data, confirm activity IDs match the source, do not over-attribute causes, do not commit to recovery dates the schedule does not support.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide the delta.** Paste baseline vs current dates for the affected activities, plus any recovery activities planned in the schedule.
4. **Ask AI to describe, not explain.** Prompt the AI to produce the §7 narrative grounded only in the delta data. Causes are stated as observations of what the schedule shows, not as conclusions about why something happened.
5. **Recompute the numbers.** Verify the variance numbers in the draft match the delta. Replace any number the AI guessed.
6. **Strip overclaims.** Remove any sentence that asserts a cause the data does not show. Convert "Team Y delayed the integration" into "the integration activity started N days after planned start; schedule does not record a cause."
7. **Add real causes only with attribution.** If a real cause is known to Tom and confirmed by the activity owner, add it as a separately marked sentence with attribution. Do not let the AI generate the attribution.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Variance numbers recomputed against the delta.
- Activity IDs cited and accurate.
- Causes framed as observations or attributed to a named owner.
- Recovery posture references real recovery activities in the schedule.
- Total length is short.

Red flags:
- A cause sentence with no attribution.
- A recovery date that does not match a recovery activity in the schedule.
- AI-generated activity IDs that are not in the delta.
- Numbers that do not match the delta when recomputed.
- Smoothing language ("minor slip") for variance that is not minor.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": delta snapshot, tool, operator, reviewer (scheduler), accountable owner (program lead), date, outcome, storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI fabricates a cause to make the narrative read better.
- AI commits to a recovery date that does not appear in the schedule.
- Narrative smooths a material slip into a non-event.
- Variance numbers in the draft do not match the delta.
- Reviewer signs off without recomputing.

Escalation triggers (stop iterating the AI draft, go to a human):
- The real cause is sensitive (customer behavior, contract dispute, personnel issue) - frame as observation, escalate to program lead.
- Recovery requires authority Tom does not have - go to program lead.
- The variance affects safety, compliance, or contract obligations - go to program lead and accountable owner directly.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic delta, Personal AI tool, Standard review, sign-off line. Tom drafts; scheduler and program lead are accountable for any real narrative.
- **Employer-deployable form (after approval):** Real variance data, Employer-approved AI tool against approved scope, Strict review (recompute every number; remove every overclaim), accountable owner is the program lead, full audit envelope, stored in approved venue.
- **Re-approval triggers:** Broadening scope from variance description to root-cause analysis; including financial or EVM linkage; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0016 (Phase 8 deliverable; this card is the Phase 4 workflow that pairs with it).
- Paired Phase 5 prompt: P-05 Schedule Variance Narrative (`05_PROMPTS/P-05-schedule-variance-narrative.md`, backlog A-0047).
- Related workflows: W-04 (schedule health review), W-06 (EVM variance explanation), W-13 (cross-tool mismatch).
