# W-11-sop-draft-generation - SOP draft generation

## Workflow identity

- **ID:** W-11
- **Backlog ID:** A-0014 (Phase 10 - SOPs and lessons learned)
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

SOP draft generation.

## 2. PM/Ops problem addressed

SOPs are often missing, out of date, or written as idealized guesses rather than as the process people actually follow. When AI is used to draft an SOP from a thin description, it invents steps that look reasonable but do not match the real process. The result is an SOP a new operator cannot follow and an experienced operator does not recognize.

## 3. Intended outcome

A first-draft SOP that captures the observed process (not an AI guess) with explicit purpose, scope, inputs, steps, controls, owner, and review cadence. Each step is testable: a new operator could execute it without the original author present. The process owner signs off before the SOP is published.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real SOP content is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for the SOP content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict if the SOP will be formally adopted.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): SOP and lessons-learned outputs.

## 5. Safe inputs

- Synthetic process observations for a fictional process.
- Generic SOP examples from public material.
- Tom's own notes from observing his own personal processes (study routine, drafting routine).

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real process observations from any employer system without explicit approval.
- Real owner names, real tool names tied to restricted systems, real customer or contract touch points.
- SOP steps that reveal restricted technical or program content.

## 7. Output format

A Markdown SOP draft with these sections, in this order:

1. **Purpose** - one paragraph stating why the SOP exists and what good looks like.
2. **Scope** - what the SOP covers and what it does not.
3. **Owner** - named role (not individual).
4. **Inputs** - what triggers the SOP and what materials it needs.
5. **Steps** - numbered, verb-led, testable. Each step is one observable action.
6. **Controls** - quality checks built into the process; how the operator confirms each step succeeded.
7. **Outputs** - what the SOP produces and where it goes.
8. **Exceptions** - documented variations and what to do when the path branches.
9. **Review cadence** - when the SOP is revisited; named owner.
10. **Open questions** - 0-3 bullets to resolve before publication.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic process observations. Same workflow runs unchanged in an Employer-approved AI tool against approved process content; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom for synthetic practice. For real SOPs, the process owner is the accountable approver; no draft becomes an active SOP until the owner has read it and confirmed it matches the process. Review intensity from §4 applies. Reviewer follows the "SOP and lessons-learned outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: confirm the SOP describes the actual process, confirm steps are testable, confirm lessons do not name individuals in a way that violates fairness or policy.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide process observations.** Paste step-by-step observations of the real process, ideally captured by watching the process or interviewing the operator. Do not let AI infer steps it has not been shown.
4. **Ask AI to structure observations into the §7 sections.** Forbid the AI from adding steps not in the observations. Steps with missing detail are marked "missing detail - confirm with operator."
5. **Verify each step is testable.** A step like "review the report" is not testable; "open the report, confirm the variance row exists, copy the variance number into the status doc" is. Edit any step that is not testable.
6. **Define controls.** For each step or step group, name how the operator confirms it succeeded (a value visible, a checkbox checked, a confirmation message received).
7. **Process-owner sign-off.** For real SOPs, the process owner reads the draft and confirms it matches the process. No publication until sign-off.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, process-owner sign-off plus the full audit envelope per §12.

## 11. Quality checks

Good output:
- Every step is observable and testable by a new operator.
- Every step has a control that confirms success.
- Inputs, outputs, owner, and review cadence are all populated.
- Exceptions are documented, not hidden inside steps.
- Open questions are explicit, not glossed over.

Red flags:
- Step that includes the word "appropriately," "as needed," or "review" without testable detail.
- Control that is "operator confirms" without naming what to confirm.
- Steps the original observations do not show.
- Owner field listing a specific individual rather than a role.
- Review cadence missing.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": process observations, tool, operator, reviewer (process owner), accountable owner (process owner), date, outcome (published, edited, deferred), storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI invents steps that look reasonable but do not match the process.
- Steps are too high-level to test.
- Controls are missing or generic.
- Owner is an individual rather than a role.
- SOP is published before the process owner has confirmed it.

Escalation triggers (stop iterating the AI draft, go to a human):
- The observations themselves are incomplete - go to the operator for a re-observation.
- The process touches safety, compliance, or contract obligations - involve compliance and program leadership before publishing.
- Process observations turn out to involve Prohibited content - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic process observations, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real process observations, Employer-approved AI tool against approved scope, Strict review (testability check; control check), process-owner sign-off, full audit envelope, stored in approved venue.
- **Re-approval triggers:** SOPs covering safety, compliance, contract, or customer-facing processes; new tool environment; SOPs that automate steps. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0014 (Phase 10 deliverable; this card is the Phase 4 workflow that pairs with it).
- Paired Phase 5 prompt: A-0045 SOP First Draft Prompt (TBD in Phase 5).
- Related template: A-0057 SOP Template (Phase 10).
- Related workflows: W-10 (lessons learned capture).
