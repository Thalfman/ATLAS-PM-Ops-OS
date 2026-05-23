# W-12-executive-brief-generation - Executive brief generation

## Workflow identity

- **ID:** W-12
- **Backlog ID:** A-0067
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Executive brief generation.

## 2. PM/Ops problem addressed

Executive briefs routinely fail in three ways: too long for the audience (a five-minute item turns into ten minutes of slides), missing the headline (the program state is unclear after reading), or overconfident (forward-looking statements presented as facts). The drafter spends time on slide polish instead of on calibrating what leadership actually needs to know.

## 3. Intended outcome

A short, leadership-ready brief with a clear headline (status color or trend), the three to five things leadership needs to know, the decisions or inputs requested, and the supporting facts traceable to the source program state. Tone is even; forward-looking statements are clearly marked.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for briefs drafted from Tom's own notes. Real program state is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic and Tom-personal inputs. Employer-approved AI tool only with explicit approval for executive content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for personal preparation. Strict for any brief that will be presented to leadership.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## 5. Safe inputs

- Synthetic program state for a fictional project (schedule headline, risk headline, financial headline).
- Tom's own preparation notes for a personal brief.
- Generic executive-brief examples from public material.

## 6. Prohibited inputs

- Real program state from any employer system without explicit approval.
- Real customer-facing detail, real contract value, real financial outlook.
- Restricted technical or compliance detail.

## 7. Output format

A short Markdown brief with these sections, designed to fit on one page or two slides:

1. **Headline** - one line; status color or trend plus the single most important fact.
2. **What leadership needs to know** - 3-5 bullets, each citing a source fact.
3. **Decisions or inputs requested** - 0-3 bullets; only if real decisions are needed.
4. **Risks and forward-looking statements** - 1-3 bullets, each clearly marked as forward-looking.
5. **Source facts (appendix)** - the underlying facts the brief draws from, traceable to the program state.

Total length: roughly 200-350 words for the body. Source-fact appendix can be longer.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic or Tom-personal input. Same workflow runs unchanged in an Employer-approved AI tool against approved program state; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. For an employer-deployable brief, the accountable owner is the program lead. Review intensity from §4 applies. Reviewer follows the "Status and reporting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: verify every claim has a source, strip language that implies certainty the source does not support, confirm forward-looking statements are clearly marked, confirm risks are stated and not hidden.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Assemble source facts.** Collect schedule headline, risk headline, financial headline, decisions pending, recent inflection points. Each source fact is one observable item.
4. **Ask AI to compress, not invent.** Prompt the AI to produce the §7 brief from the source facts. Forbid the AI from adding facts not in the source list. Forbid certainty language not supported by the source.
5. **Read against the source list.** Confirm every body bullet traces to a source fact. Mark forward-looking statements clearly.
6. **Calibrate length.** If the brief is longer than 350 words, cut. Length growth usually means the AI added context the source did not.
7. **Confirm with the program lead** (employer-deployable). Brief is not presented until the program lead has agreed the headline and the bullets reflect their view.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the document. For employer-deployable runs, program-lead sign-off plus full audit envelope per §12.

## 11. Quality checks

Good output:
- Headline is one line and unambiguous.
- Every bullet traces to a source fact.
- Forward-looking statements are marked.
- Decisions requested are real and actionable.
- Total length fits on a page.

Red flags:
- Headline that hedges ("status is mixed").
- Bullets that "round" toward a more positive read than the source supports.
- Forward-looking statements presented as facts.
- Decisions requested that are not actually decisions the audience can make.
- Source-fact appendix that does not match the body.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": source facts, tool, operator, reviewer (program lead), accountable owner, date, outcome (presented, withdrawn, edited), storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI invents a headline the source facts do not support.
- AI smooths a real concern into neutral language.
- Forward-looking statements get unmarked between iterations.
- Decisions requested are framed in a way that pre-decides the answer.
- Reviewer signs off without engaging the source-fact appendix.

Escalation triggers (stop iterating the AI draft, go to a human):
- Headline involves safety, compliance, or customer-facing impact - go to program lead before drafting.
- A decision requested would commit the program in a way Tom does not have authority to frame - go to program lead.
- Source facts turn out to include Prohibited content - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic or Tom-personal source facts, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real program state, Employer-approved AI tool against approved scope, Strict review (every bullet traced to source; every forward-looking statement marked), program-lead sign-off, full audit envelope, stored in approved venue.
- **Re-approval triggers:** Briefs that include customer-facing or contract-bearing content; briefs to external stakeholders; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0067.
- Paired Phase 5 prompt: A-0044 Executive Brief Drafting Prompt (TBD in Phase 5).
- Related template: `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`.
- Related workflows: W-01 (weekly status report), W-05 (schedule variance narrative), W-06 (EVM variance explanation).
