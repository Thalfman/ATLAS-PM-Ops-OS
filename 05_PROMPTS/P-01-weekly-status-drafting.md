# P-01-weekly-status-drafting - Weekly status drafting

## Prompt identity

- **ID:** P-01
- **Paired workflow:** W-01 (`04_WORKFLOWS/W-01-weekly-status-report.md`)
- **Backlog ID:** A-0039
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Draft a short, executive-readable weekly status narrative from a source list of facts the reviewer can point to. The prompt addresses the three failure modes named in W-01 §2: too technical for leadership, disconnected from underlying schedule/risk/finance reality, or inconsistent week over week. The deliverable is the six-section narrative described in W-01 §7 (Period covered, Accomplishments, Schedule movement, Risks and issues, Decisions needed, Next steps).

## 2. Paired workflow and PM/Ops role

Paired with `W-01-weekly-status-report.md`. Executes step 4 ("Ask AI to structure, not invent") of the W-01 §10 process. AI role: structure the source bullets into the §7 output format. AI must not add facts, invent dates or owners, soften risks, or convert open items into accomplishments.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for first drafts from Tom's own notes. Never Employer-approved in a personal AI tool.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first). Employer-approved AI tool only if and when the employer approves it for status reporting against employer-approved data.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for personal preparation. Strict when the narrative will be shared with leadership.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## 4. Safe input requirements

Mirror W-01 §5:

- Synthetic milestone list with fictional dates and owners.
- Tom's own notes from public meetings, training, or personal preparation activity.
- Synthetic accomplishment, risk, issue, and next-step bullets authored by Tom.
- Generic, public references (PMI material, vendor documentation) where useful as scaffolding.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-01 §6:

- Real employer status reports, internal schedules, or program names.
- Real customer, contract, or financial details.
- Internal technical content, real meeting notes, real Microsoft Project files, or real accounting exports.
- Any paraphrased restricted content. Paraphrased restricted content is restricted content (per `DATA_SENSITIVITY_DECISION_MODEL.md` "Things that look safer than they are").

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[SYNTHETIC_PERIOD]` — fictional reporting period (e.g., "Week of 2026-06-08 to 2026-06-12").
- `[APPROVED_INPUT]` — the source-fact list (one bullet per observable fact).
- `[PLACEHOLDER_OWNER]` — fictional or Tom-personal owner name(s) for next-step bullets.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional draft a weekly status narrative.

ROLE
- Structure source bullets into a status report.
- Do not add facts that are not in the source list.
- Do not invent dates, owners, percentages, or numbers.
- Do not soften risks into accomplishments.
- Do not convert open decisions into closed decisions.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Period covered: [SYNTHETIC_PERIOD]
- Source fact bullets (one observable fact per bullet):
[APPROVED_INPUT]
- Known next-step owners: [PLACEHOLDER_OWNER]

OUTPUT FORMAT
Return a Markdown narrative with these sections, in this exact order:

1. **Period covered** (one line)
2. **Accomplishments** (3-5 bullets, verb-led, each pointing to a source fact)
3. **Schedule movement** (3-5 bullets; flag what moved, what is at risk, what is on track; cite source facts)
4. **Risks and issues** (3-5 bullets; condition-consequence form where the source supports it; do not invent triggers)
5. **Decisions needed** (0-3 bullets; only if the source list names a real decision)
6. **Next steps** (3-5 bullets, verb-led, owner-tagged; owners must come from the input)

LENGTH
- Total body: 300-500 words. Do not exceed 500.
- Forward-looking statements must be marked: prepend with "Forward-looking:" or wrap in parentheses with "(forward-looking)".

DISCIPLINE
- If a source bullet is ambiguous, label the matching output bullet "(source unclear — confirm)" rather than guessing.
- If a field has no source content (e.g., no decisions are pending), leave that section header followed by "(none this period)".
- After the narrative, append a short "Source trace" list: each output bullet's number followed by the source bullet(s) it traces to. This is for the reviewer's source-trace step, not for the audience.

Return the narrative and the source trace only. Do not add a cover note, status color, or executive summary unless the source list contains one.
```

## 8. Expected output

A Markdown narrative with six labeled sections (Period covered, Accomplishments, Schedule movement, Risks and issues, Decisions needed, Next steps) totaling 300-500 words, followed by a "Source trace" list mapping each body bullet to the source fact it came from. Mirrors W-01 §7.

## 9. Human review checklist

The reviewer (Tom by default; program lead for employer-deployable runs) follows the "Status and reporting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist in the same file before using the output:

- Verify every claim has a source the reviewer can point to (use the source-trace list).
- Strip language that implies certainty the source does not support.
- Confirm forward-looking statements are clearly marked as forward-looking.
- Confirm risks are stated, not hidden.
- Check that schedule and risk items are concrete (named milestone, named risk, dated event).
- Confirm tone is even — no marketing language, no blame language.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-01 §13):

- AI fabricates a milestone, owner, date, or number that is not in the source bullets.
- AI converts an open risk into a closed accomplishment.
- AI smooths a real conflict into neutral language that hides the decision needed.
- Tone drift toward marketing or self-promotion.
- Reviewer skips the source-trace step and signs off on plausibility alone.

Escalation triggers:

- The source list itself is wrong or incomplete — go to the original owner; do not iterate the AI draft.
- The "decisions needed" section names a real decision Tom is not empowered to frame — go to manager.
- A risk crosses into safety, compliance, or contract territory — go to the accountable owner.
- The data category turns out to be Prohibited — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic or Tom-personal source bullets, Personal AI tool, Standard review, sign-off line in the output. No real employer content.
- **Employer-deployable form (after approval):** Employer-approved status source material, Employer-approved AI tool against approved scope, Strict review, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," accountable owner sign-off inside the approved venue. The §7 prompt text is unchanged; only the data category, tool environment, review intensity, and audit recording change.
- **Re-approval triggers:** New data category in the input (e.g., financial detail added); new tool environment; new accountable owner; any change that broadens scope. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm every source-fact bullet is observable. If a bullet is opinion or forecast, mark it as such in the input.
- Confirm next-step owners in the input are fictional or Tom-personal (not real employer staff) for personal-preparation runs.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before sign-off. Required for Strict review intensity (any narrative going to leadership). Recommended for Standard.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-01-weekly-status-report.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0039.
- Related template: `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`.
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-02-meeting-notes-to-actions.md`, `P-03-action-aging-summary.md`, `P-12-executive-brief-drafting.md`.
