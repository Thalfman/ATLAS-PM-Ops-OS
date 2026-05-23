# P-05-schedule-variance-narrative - Schedule variance narrative drafting

## Prompt identity

- **ID:** P-05
- **Paired workflow:** W-05 (`04_WORKFLOWS/W-05-schedule-variance-narrative.md`)
- **Backlog ID:** A-0047
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Draft a short schedule variance narrative grounded in a baseline-vs-current delta: what variance is present, what activities drive it, what the apparent (not asserted) cause is, what the recovery posture looks like, and what decision or input is needed. The prompt addresses W-05 §2: variance reported as a number without narrative, or narrative that overclaims/under-claims. The deliverable is the five-section short narrative described in W-05 §7.

## 2. Paired workflow and PM/Ops role

Paired with `W-05-schedule-variance-narrative.md`. Executes step 4 of the W-05 §10 process ("Ask AI to describe, not explain"). AI role: describe the delta in PM/Ops language; frame causes as observations of what the schedule shows, not as conclusions. AI must not assert causes the delta does not show, commit to recovery dates the schedule does not contain, or invent activity IDs.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic only for personal preparation. Real schedule deltas are Employer-approved and route only to an Employer-approved AI tool with explicit scope approval.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only when both the variance data and the tool have explicit approval.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real variance narrative.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Schedule outputs.

## 4. Safe input requirements

Mirror W-05 §5:

- Synthetic schedule delta showing baseline vs current dates for a fictional project.
- Generic variance examples from public PMI material.
- Tom's own notes from public schedule-analysis training.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-05 §6:

- Real schedule deltas from any employer system without explicit approval.
- Real activity names, IDs, baselines, or owner attribution.
- Restricted causal explanations (customer behavior, contract changes, real technical issues).

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[SYNTHETIC_PERIOD]` — fictional reporting period.
- `[FICTIONAL_ACTIVITY_ID]` — fictional activity IDs in the delta.
- `[APPROVED_INPUT]` — the baseline-vs-current delta block (activity ID, name, baseline start/finish, current start/finish, delta in days, owner if known, and any recovery activities).
- `[PLACEHOLDER_OWNER]` — fictional activity owner names.
- `[FICTIONAL_VARIANCE]` — the headline variance figure (e.g., "+12 days on the critical path").

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional draft a schedule variance narrative from a baseline-vs-current delta.

ROLE
- Describe the delta in PM/Ops language.
- Frame apparent causes as observations of what the schedule shows.
- Do not assert causes the delta does not show.
- Do not commit to recovery dates the schedule does not contain.
- Do not invent activity IDs, names, or owners.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Period: [SYNTHETIC_PERIOD]
- Headline variance: [FICTIONAL_VARIANCE]
- Baseline-vs-current delta (one row per affected activity; include activity ID, name, baseline start/finish, current start/finish, delta in days, owner):
[APPROVED_INPUT]
- Known activity owners: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown narrative with these sections, in this order:

1. **Variance summary** — one paragraph with the headline numbers (days slipped, paths affected). Numbers must come from the delta.
2. **What moved** — 3-5 bullets, each citing activity ID [FICTIONAL_ACTIVITY_ID format] and the magnitude of the move in days.
3. **Apparent cause (observed, not asserted)** — 1-3 bullets framed as observations ("activity X started N days after planned start; the schedule does not record a cause"). Do not attribute cause to a person, team, vendor, or customer unless the delta input names them.
4. **Recovery posture** — 1-3 bullets on what the schedule shows planned for recovery. Each bullet must reference a real recovery activity in the input. Name the activity owner.
5. **Decisions or inputs needed** — 0-3 bullets. Only if the delta shows a decision is required (e.g., a recovery activity has no owner, or a dependency is missing).

LENGTH
- Total: 250-400 words. Do not exceed 400.

DISCIPLINE
- If a variance number cannot be recomputed from the delta, do not include it. Flag it as "variance number not in delta."
- If apparent cause cannot be observed from the delta, write "schedule does not record a cause" rather than inventing one.
- If no recovery activity is in the delta for a moved item, write "no recovery activity in current schedule" — do not invent one.
- Append a short "Number trace" list: for each variance figure in the narrative, the matching activity IDs and the arithmetic that produced it.

Return the narrative and the number trace only.
```

## 8. Expected output

A Markdown narrative with five labeled sections (Variance summary, What moved, Apparent cause, Recovery posture, Decisions or inputs needed) totaling 250-400 words, followed by a "Number trace" list. Mirrors W-05 §7.

## 9. Human review checklist

The reviewer (Tom; scheduler and program lead for employer-deployable runs) follows the "Schedule outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before using the output:

- Recompute or sanity-check variance percentages and durations against the delta.
- Confirm the narrative matches the underlying data.
- Confirm activity names and IDs match the source.
- Confirm the narrative does not over-attribute causes or commit to recovery dates the schedule does not support.
- Confirm recovery posture references real recovery activities in the schedule.
- Confirm "schedule does not record a cause" appears wherever the delta does not show one.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-05 §13):

- AI fabricates a cause to make the narrative read better.
- AI commits to a recovery date that does not appear in the schedule.
- Narrative smooths a material slip into a non-event.
- Variance numbers in the draft do not match the delta.
- Reviewer signs off without recomputing.

Escalation triggers:

- The real cause is sensitive (customer behavior, contract dispute, personnel issue) — frame as observation, escalate to program lead.
- Recovery requires authority Tom does not have — go to program lead.
- The variance affects safety, compliance, or contract obligations — go to program lead and accountable owner directly.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic delta, Personal AI tool, Standard review, sign-off line. Tom drafts; scheduler and program lead are accountable for any real narrative.
- **Employer-deployable form (after approval):** Real variance data, Employer-approved AI tool against approved scope, Strict review (recompute every number; remove every overclaim), accountable owner is the program lead, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," stored in approved venue.
- **Re-approval triggers:** Broadening scope from variance description to root-cause analysis; including financial or EVM linkage; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm activity IDs, names, and owners in the delta are fictional or public for personal-preparation runs.
- Confirm the delta does not include any real `.mpp` export content.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before sign-off. Required for Strict review intensity.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-05-schedule-variance-narrative.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0047 (also references A-0016 Schedule Variance Narrative Template in Phase 8).
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-06-evm-variance-explanation.md`, `P-09-accounting-reconciliation-narrative.md`.
