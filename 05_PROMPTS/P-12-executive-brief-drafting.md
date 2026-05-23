# P-12-executive-brief-drafting - Executive brief drafting

## Prompt identity

- **ID:** P-12
- **Paired workflow:** W-12 (`04_WORKFLOWS/W-12-executive-brief-generation.md`)
- **Backlog ID:** A-0044
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Compress a source-fact list (schedule headline, risk headline, financial headline, decisions pending, recent inflection points) into a leadership-ready brief with a clear headline, three to five things leadership needs to know, decisions or inputs requested, risks and forward-looking statements, and a source-fact appendix. The prompt addresses W-12 §2: briefs that are too long, miss the headline, or overclaim. The deliverable is the five-section brief shape described in W-12 §7.

## 2. Paired workflow and PM/Ops role

Paired with `W-12-executive-brief-generation.md`. Executes steps 4-6 of the W-12 §10 process: compress source facts, mark forward-looking statements, calibrate length. AI role: compress without invention; flag forward-looking statements; trace every body bullet to a source fact. AI must not invent the headline, add context the source did not contain, smooth concerns, or pre-decide a decision.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for briefs drafted from Tom's own notes. Real program state is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic and Tom-personal inputs. Employer-approved AI tool only with explicit approval for executive content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for personal preparation. Strict for any brief that will be presented to leadership.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## 4. Safe input requirements

Mirror W-12 §5:

- Synthetic program state for a fictional project (schedule headline, risk headline, financial headline).
- Tom's own preparation notes for a personal brief.
- Generic executive-brief examples from public material.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-12 §6:

- Real program state from any employer system without explicit approval.
- Real customer-facing detail, real contract value, real financial outlook.
- Restricted technical or compliance detail.

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[SYNTHETIC_PERIOD]` — fictional period or as-of date.
- `[APPROVED_INPUT]` — source-fact list (one observable fact per bullet, covering schedule headline, risk headline, financial headline, decisions pending, recent inflection points).
- `[PLACEHOLDER_OWNER]` — fictional decision-owner or accountable-owner names that may appear.
- `[STATUS_COLOR_OR_TREND]` — green/yellow/red, or "improving/holding/declining" — only if the source list contains it; otherwise omit.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional draft a one-page executive brief.

ROLE
- Compress the source facts into a short, leadership-ready brief.
- Do not add facts not in the source list.
- Do not use certainty language the source does not support.
- Mark every forward-looking statement clearly.
- Do not pre-decide a decision the audience is meant to make.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Period or as-of: [SYNTHETIC_PERIOD]
- Headline color / trend (only if source supplies it): [STATUS_COLOR_OR_TREND]
- Source facts (one observable fact per bullet):
[APPROVED_INPUT]
- Known decision-owner / accountable-owner names: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown brief with these sections, designed to fit on one page or two slides:

1. **Headline** — one line; the status color or trend (if known) plus the single most important fact.
2. **What leadership needs to know** — 3-5 bullets, each citing the source fact it traces to.
3. **Decisions or inputs requested** — 0-3 bullets. Only if real decisions are needed. Each bullet states the question without pre-deciding the answer.
4. **Risks and forward-looking statements** — 1-3 bullets, each clearly marked as forward-looking (prepend "Forward-looking:" or wrap in parentheses with "(forward-looking)").
5. **Source facts (appendix)** — the underlying facts the brief draws from, numbered, traceable.

LENGTH
- Body sections 1-4: 200-350 words. Do not exceed 350.
- Source-fact appendix: no length limit, but each fact is one observable item.

DISCIPLINE
- If the source list does not supply a status color or trend, do not invent one. The Headline section uses the single most important fact only.
- If a body bullet does not trace to a source fact, do not include it.
- If a "decision needed" cannot be framed without pre-deciding the answer, write "[decision framing requires program lead input]" — do not invent the framing.
- If a forward-looking statement is in the source as a fact, restate it as a forward-looking statement, not as a fact.

Return the brief and the appendix only.
```

## 8. Expected output

A Markdown brief with five labeled sections (Headline, What leadership needs to know, Decisions or inputs requested, Risks and forward-looking statements, Source facts appendix), body sections 1-4 fitting in 200-350 words. Mirrors W-12 §7.

## 9. Human review checklist

The reviewer (Tom; program lead for employer-deployable runs) follows the "Status and reporting outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before presentation:

- Verify every claim has a source the reviewer can point to (use the source-fact appendix).
- Strip language that implies certainty the source does not support.
- Confirm forward-looking statements are clearly marked.
- Confirm risks are stated, not hidden.
- Confirm the headline is one line and unambiguous (no hedging like "status is mixed").
- Confirm decisions requested are real and actionable, not pre-decided.
- Confirm total length fits on a page (200-350 words for the body).

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-12 §13):

- AI invents a headline the source facts do not support.
- AI smooths a real concern into neutral language.
- Forward-looking statements get unmarked between iterations.
- Decisions requested are framed in a way that pre-decides the answer.
- Reviewer signs off without engaging the source-fact appendix.

Escalation triggers:

- Headline involves safety, compliance, or customer-facing impact — go to program lead before drafting.
- A decision requested would commit the program in a way Tom does not have authority to frame — go to program lead.
- Source facts turn out to include Prohibited content — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic or Tom-personal source facts, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real program state, Employer-approved AI tool against approved scope, Strict review (every bullet traced to source; every forward-looking statement marked), program-lead sign-off, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," stored in approved venue.
- **Re-approval triggers:** Briefs that include customer-facing or contract-bearing content; briefs to external stakeholders; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm every source fact is observable. Opinion or forecast belongs in §4 (Risks and forward-looking statements), not in the body bullets.
- Confirm placeholder owners are fictional for personal-preparation runs.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before presentation. Required for Strict review intensity (any brief going to leadership).

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-12-executive-brief-generation.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0044.
- Related template: `07_TEMPLATES/EXECUTIVE_NARRATIVE.md`.
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-01-weekly-status-drafting.md`, `P-05-schedule-variance-narrative.md`, `P-06-evm-variance-explanation.md`.
