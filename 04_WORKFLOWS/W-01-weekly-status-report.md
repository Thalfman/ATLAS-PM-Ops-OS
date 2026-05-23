# W-01-weekly-status-report - AI-assisted weekly status report drafting

## Workflow identity

- **ID:** W-01
- **Backlog ID:** A-0008
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

AI-assisted weekly status report drafting.

## 2. PM/Ops problem addressed

Weekly status reports drift into one of three failure modes: too technical for leadership, disconnected from the underlying schedule/risk/finance reality, or inconsistent week over week so that movement is hard to read. The drafter spends time on prose instead of on the underlying facts, and the reviewer can no longer tell what changed.

## 3. Intended outcome

A short, executive-readable status narrative with consistent sections (accomplishments, schedule movement, risks and issues, decisions needed, next steps), grounded in source facts the reviewer can point to, with overclaims and tone problems removed before sharing.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for first drafts from Tom's own notes. Never Employer-approved in a personal AI tool.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for synthetic and Tom-personal inputs. Employer-approved AI tool only if and when the employer approves it for status reporting against employer-approved data.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for personal preparation. Strict when the narrative will be shared with leadership.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## 5. Safe inputs

- Synthetic milestone list with fictional dates and owners.
- Tom's own notes from public meetings, training, or personal preparation activity.
- Synthetic accomplishment, risk, issue, and next-step bullets authored by Tom.
- Generic, public references (PMI material, vendor documentation) where useful as scaffolding.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real employer status reports, internal schedules, or program names.
- Real customer, contract, or financial details.
- Internal technical content, real meeting notes, real Microsoft Project files, or real accounting exports.
- Any paraphrased restricted content. Paraphrased restricted content is restricted content (per `DATA_SENSITIVITY_DECISION_MODEL.md` "Things that look safer than they are").

## 7. Output format

A short Markdown narrative or document with these sections, in this order:

1. **Period covered** (one line).
2. **Accomplishments** (3-5 bullets, verb-led, each pointing to a source fact).
3. **Schedule movement** (3-5 bullets; flag what moved, what is at risk, what is on track).
4. **Risks and issues** (3-5 bullets; condition-consequence form where relevant).
5. **Decisions needed** (0-3 bullets; only if there are real decisions).
6. **Next steps** (3-5 bullets, verb-led, owner-tagged).

Total length: roughly 300-500 words. Longer than that usually means the narrative is doing the underlying analysis's job.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic or Tom-personal input. The same workflow runs unchanged in an Employer-approved AI tool against Employer-approved status content, once that approval exists; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. For an employer-deployable run, the accountable owner is the project or program lead who signs off the status before it is shared. Review intensity from §4 applies. The reviewer follows the "Status and reporting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: verify every claim has a source, strip language that implies certainty the source does not support, mark forward-looking statements, confirm risks are stated and not hidden.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Assemble source facts.** Collect the synthetic or Tom-personal source bullets covering accomplishments, schedule movement, risks/issues, decisions, next steps. Each source bullet is one observable fact with no narrative around it.
4. **Ask AI to structure, not invent.** Prompt the AI to organize the source bullets into the §7 output format. Forbid the AI from adding facts not in the source list.
5. **Read the draft against the source list.** Mark anything in the draft that does not trace to a source bullet for deletion or rephrasing.
6. **Calibrate tone.** Remove certainty language the source does not support. Mark forward-looking statements as forward-looking. Confirm risks are stated, not hidden.
7. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
8. **Record sign-off.** Standard intensity: sign-off line in the document ("Reviewed by Tom YYYY-MM-DD"). Strict intensity (employer-deployable): full audit envelope per §12.

## 11. Quality checks

Good output:
- Every claim traces to a source bullet.
- Schedule and risk items are concrete (named milestone, named risk, dated event).
- Tone is even; no marketing language, no blame language.
- Forward-looking statements are marked.
- Reads end-to-end in under three minutes.

Red flags:
- A bullet that "sounds plausible" but cannot be traced to a source.
- Numbers that don't appear in any source fact.
- Causes attributed to people or teams the source does not name.
- Risks softened into accomplishments.
- The draft is longer than the source list of facts.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": source, tool, operator, reviewer, accountable owner, date, outcome, storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI fabricates a milestone, owner, date, or number that is not in the source bullets.
- AI converts an open risk into a closed accomplishment.
- AI smooths a real conflict into neutral language that hides the decision needed.
- Tone drift toward marketing or self-promotion.
- Reviewer skips the source-trace step and signs off on plausibility alone.

Escalation triggers (stop iterating the AI draft, go to a human):
- The source list itself is wrong or incomplete - go to the original owner.
- The "decisions needed" section names a real decision Tom is not empowered to frame - go to manager.
- A risk crosses into safety, compliance, or contract territory - go to the accountable owner.
- The data category turns out to be Prohibited under `DATA_SENSITIVITY_DECISION_MODEL.md` - stop, do not use AI.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic or Tom-personal source bullets, Personal AI tool, Standard review, sign-off line in the output. No real employer content.
- **Employer-deployable form (after approval):** Employer-approved status source material, Employer-approved AI tool against approved scope, Strict review, full audit envelope, accountable owner sign-off inside the approved venue. The §10 process is unchanged; only the data category, tool environment, review intensity, and audit recording change.
- **Re-approval triggers:** New data category in the input (e.g., financial detail added); new tool environment; new accountable owner; any change that broadens scope. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0008.
- Template: `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`.
- Paired Phase 5 prompt: A-0039 Weekly Status Drafting Prompt (TBD in Phase 5).
- Related workflows: W-02 (meeting notes to actions), W-03 (action item aging), W-12 (executive brief generation).
