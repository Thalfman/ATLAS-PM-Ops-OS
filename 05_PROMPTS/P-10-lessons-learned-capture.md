# P-10-lessons-learned-capture - Lessons learned capture

## Prompt identity

- **ID:** P-10
- **Paired workflow:** W-10 (`04_WORKFLOWS/W-10-lessons-learned-capture.md`)
- **Backlog ID:** A-0046
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Convert a set of raw event notes into a short lessons-learned record: event, what happened, what was expected, gap, apparent root cause (as observation, not blame), recommended change, SOP update candidate, owner and follow-up. The prompt addresses W-10 §2: lessons captured too late, too high-level, or framed in language that names individuals unfairly. The deliverable is the eight-section record described in W-10 §7.

## 2. Paired workflow and PM/Ops role

Paired with `W-10-lessons-learned-capture.md`. Executes step 4 of the W-10 §10 process ("Ask AI to structure, not blame"). AI role: structure event notes into the §7 record; frame apparent root cause as process / information-flow / tool issues, never as individual blame; identify SOP update candidates. AI must not name individuals, invent event detail, or propose vague recommendations.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real lessons-learned content is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for the lessons content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): SOP and lessons-learned outputs.

## 4. Safe input requirements

Mirror W-10 §5:

- Synthetic event notes for a fictional project.
- Generic lessons-learned examples from public PMI material.
- Tom's own notes from public training or his own non-restricted observations.

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-10 §6:

- Real event notes that name real individuals, teams, or vendors in identifiable ways.
- Real customer-impact descriptions, real contract or financial impact detail.
- Restricted program structure or technical content tied to the event.

## 6. Placeholders used

- `[SYNTHETIC_PROJECT_NAME]` — fictional project name.
- `[SYNTHETIC_EVENT_TITLE]` — fictional event name (e.g., "Integration test schedule slip").
- `[SYNTHETIC_DATE]` — fictional event date.
- `[APPROVED_INPUT]` — raw event notes block (time-ordered observations; strip identifying detail the lesson does not need).
- `[PLACEHOLDER_OWNER]` — fictional change-owner name.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional draft a lessons-learned record from event notes.

ROLE
- Structure event notes into a lessons-learned record.
- Frame apparent root cause as process / information-flow / tool issues.
- Do not name individuals or teams in the root-cause section.
- Do not invent event detail that does not appear in the notes.
- Do not propose vague recommendations ("communicate better"); concrete change only.

INPUTS
- Project: [SYNTHETIC_PROJECT_NAME]
- Event: [SYNTHETIC_EVENT_TITLE] on [SYNTHETIC_DATE]
- Raw event notes (time-ordered observations):
[APPROVED_INPUT]
- Known change-owner candidates: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown record with these sections, in this order:

1. **Event** — one line ([SYNTHETIC_EVENT_TITLE] on [SYNTHETIC_DATE]).
2. **What happened** — 2-4 bullets, observable, time-ordered. Each bullet ties to a line in the input notes.
3. **What was expected** — 1-3 bullets describing the planned or assumed behavior.
4. **Gap** — 1-2 bullets stating the difference between what happened and what was expected.
5. **Apparent root cause (observation, not blame)** — 1-3 bullets framed as observations about process, information flow, or tools. No individual or team names.
6. **Recommended change** — 1-3 bullets naming a concrete change (process, SOP, training, tool, communication). Each bullet is testable: a reader can tell whether the change was made.
7. **SOP update candidate** — 0-2 bullets naming the SOP that would need updating; flag if a new SOP is needed.
8. **Owner and follow-up** — named owner from inputs, target date for the change.

DISCIPLINE
- Replace any individual or team attribution in apparent root cause with process or information-flow framing.
- If the notes name individuals, do not propagate the names into the record; reference the role or the process touchpoint instead.
- If a section has no source content (e.g., no SOP update candidate is obvious), write "(none identified at this time)" rather than leaving the section empty.
- Append a "Source trace" list: each bullet in sections 2, 3, 5, and 6 mapped back to the line(s) of input notes that support it.

Return the record and the source trace only.
```

## 8. Expected output

A Markdown record with eight labeled sections totaling roughly 200-400 words, followed by a "Source trace" list. Mirrors W-10 §7.

## 9. Human review checklist

The reviewer (Tom; project leadership for employer-deployable runs) follows the "SOP and lessons-learned outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before publishing:

- Confirm the SOP describes the actual event, not an AI-idealized version (analogous: confirm the lesson describes the actual event).
- Confirm bullets are testable (a reader can tell whether the change was made).
- Confirm lessons do not name individuals in a way that violates fairness or policy.
- Fairness check on root cause: re-read and replace any individual or team attribution with process or information-flow framing.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-10 §13):

- AI assigns blame to a named individual.
- Recommended change is vague or unactionable.
- Lesson omits the underlying process gap that caused the event.
- AI invents event detail that does not appear in the notes.
- Reviewer publishes before the fairness check.

Escalation triggers:

- Event involves safety, compliance, or customer impact — go to program leadership before drafting.
- Lesson would identify an individual's performance issue — separate the performance discussion from the lessons learned entry.
- Event detail turns out to involve Prohibited content — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic event notes, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real event notes, Employer-approved AI tool against approved scope, Strict review with fairness check, project leadership sign-off, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," stored in approved venue.
- **Re-approval triggers:** Lessons that involve customer, contract, or compliance impact; lessons that name individuals or teams; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm raw event notes do not name real individuals or teams. If they do, redact before sending; the prompt's no-names rule is not a substitute for safe inputs.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before publication. Required for any lesson that will be shared beyond Tom's personal preparation.

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-10-lessons-learned-capture.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0046 (also references A-0013 Lessons Learned Capture Workflow in Phase 10).
- Related template: A-0058 Lessons Learned Template (Phase 10).
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-11-sop-first-draft.md`.
