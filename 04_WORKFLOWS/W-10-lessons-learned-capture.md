# W-10-lessons-learned-capture - Lessons learned capture

## Workflow identity

- **ID:** W-10
- **Backlog ID:** A-0013 (Phase 10 - SOPs and lessons learned)
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Lessons learned capture.

## 2. PM/Ops problem addressed

Lessons learned are routinely captured too late, at too high a level, or framed in language that names individuals in ways that violate fairness or policy. The lessons get filed and never change future behavior because they were not connected to a specific event, root cause, or SOP update candidate.

## 3. Intended outcome

A short lessons-learned entry for a specific event, capturing what happened, what was expected, the gap, the apparent root cause (as observation, not blame), the recommended change, and the SOP or process update candidate. Captured close to the event so detail survives.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real lessons-learned content is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for the lessons content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): SOP and lessons-learned outputs.

## 5. Safe inputs

- Synthetic event notes for a fictional project.
- Generic lessons-learned examples from public PMI material.
- Tom's own notes from public training or his own non-restricted observations.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real event notes that name real individuals, teams, or vendors in identifiable ways.
- Real customer-impact descriptions, real contract or financial impact detail.
- Restricted program structure or technical content tied to the event.

## 7. Output format

A short Markdown record with these sections:

1. **Event** - one line.
2. **What happened** - 2-4 bullets, observable, time-ordered.
3. **What was expected** - 1-3 bullets describing the planned or assumed behavior.
4. **Gap** - 1-2 bullets stating the difference between what happened and what was expected.
5. **Apparent root cause (observation, not blame)** - 1-3 bullets framed as observations about process, information flow, or tools; do not name individuals.
6. **Recommended change** - 1-3 bullets naming a concrete change (process, SOP, training, tool, communication).
7. **SOP update candidate** - 0-2 bullets naming the SOP that would need updating; flag if a new SOP is needed.
8. **Owner and follow-up** - named owner, target date for the change.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic event notes. Same workflow runs unchanged in an Employer-approved AI tool against approved lessons content; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. For real lessons, project leadership is the accountable approver before publication; lessons that name individuals or organizations must pass an additional fairness check. Review intensity from §4 applies. Reviewer follows the "SOP and lessons-learned outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: confirm the entry describes the actual event, confirm steps and gap are testable, confirm lessons do not name individuals in a way that violates fairness or policy.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide event notes.** Paste raw event notes including time-ordered observations. Strip identifying information that the lesson does not need.
4. **Ask AI to structure, not blame.** Prompt the AI to produce the §7 record. Forbid the AI from naming individuals; require process / information-flow / tool framing for apparent root cause.
5. **Verify each section against the event notes.** Confirm the "what happened" and "what was expected" bullets are observable and tied to the notes.
6. **Fairness check on root cause.** Re-read the root cause section. Replace any individual or team attribution with process or information-flow framing.
7. **Identify SOP candidates.** Map the recommended change to an existing SOP or flag a new SOP. Cross-reference with `07_TEMPLATES/`.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, project leadership signs off before publication; full audit envelope per §12.

## 11. Quality checks

Good output:
- Event has a clear time anchor.
- What-happened bullets are observable and time-ordered.
- Gap is stated plainly.
- Root cause is process or information-flow, not individual.
- Recommended change is concrete and owned.

Red flags:
- Root cause names an individual or team in blame language.
- Recommended change is vague ("communicate better").
- SOP update candidate is missing for a non-trivial process gap.
- Lesson is high-level enough that no one could act on it.
- Sensitive program detail in the record that should not be there.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": raw event notes, tool, operator, reviewer, accountable owner (project leadership), date, outcome (published, edited, withheld), storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI assigns blame to a named individual.
- Recommended change is vague or unactionable.
- Lesson omits the underlying process gap that caused the event.
- AI invents event detail that does not appear in the notes.
- Reviewer publishes before the fairness check.

Escalation triggers (stop iterating the AI draft, go to a human):
- Event involves safety, compliance, or customer impact - go to program leadership before drafting.
- Lesson would identify an individual's performance issue - separate the performance discussion from the lessons learned entry.
- Event detail turns out to involve Prohibited content - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic event notes, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real event notes, Employer-approved AI tool against approved scope, Strict review with fairness check, project leadership sign-off, full audit envelope, stored in approved venue.
- **Re-approval triggers:** Lessons that involve customer, contract, or compliance impact; lessons that name individuals or teams; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0013 (Phase 10 deliverable; this card is the Phase 4 workflow that pairs with it).
- Paired Phase 5 prompt: A-0046 Lessons Learned Capture Prompt (TBD in Phase 5).
- Related template: A-0058 Lessons Learned Template (Phase 10).
- Related workflows: W-11 (SOP draft generation).
