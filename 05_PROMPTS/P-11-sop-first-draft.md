# P-11-sop-first-draft - SOP first draft

## Prompt identity

- **ID:** P-11
- **Paired workflow:** W-11 (`04_WORKFLOWS/W-11-sop-draft-generation.md`)
- **Backlog ID:** A-0045
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Use case

Generate a first-draft SOP from observed process steps. The draft captures purpose, scope, owner (role, not individual), inputs, steps (numbered, verb-led, testable), controls, outputs, exceptions, review cadence, and open questions. The prompt addresses W-11 §2: SOPs written as idealized guesses rather than as the process people actually follow. The deliverable is the ten-section SOP shape described in W-11 §7.

## 2. Paired workflow and PM/Ops role

Paired with `W-11-sop-draft-generation.md`. Executes steps 4-6 of the W-11 §10 process: structure observations into the §7 sections, verify steps are testable, define controls. AI role: structure, ask for missing detail, propose controls based on observed steps. AI must not add steps not in the observations or use vague verbs ("review," "appropriately," "as needed") without testable detail.

## 3. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real SOP content is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for the SOP content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict if the SOP will be formally adopted.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): SOP and lessons-learned outputs.

## 4. Safe input requirements

Mirror W-11 §5:

- Synthetic process observations for a fictional process.
- Generic SOP examples from public material.
- Tom's own notes from observing his own personal processes (study routine, drafting routine).

## 5. Prohibited input warning

In the default personal-preparation environment (§3), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §11 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

Mirror W-11 §6:

- Real process observations from any employer system without explicit approval.
- Real owner names, real tool names tied to restricted systems, real customer or contract touch points.
- SOP steps that reveal restricted technical or program content.

## 6. Placeholders used

- `[SYNTHETIC_PROCESS_NAME]` — fictional process name (e.g., "Weekly status report assembly").
- `[SYNTHETIC_OWNER_ROLE]` — fictional owner role (not individual; e.g., "PM/Ops analyst").
- `[APPROVED_INPUT]` — raw step-by-step process observations (each line one observable action).
- `[PLACEHOLDER_OWNER]` — fictional owner role names that may appear in inputs.

## 7. Copy-paste prompt text

```text
You are an assistant helping a PMP-certified PM/Ops professional draft a first-version SOP from observed process steps.

ROLE
- Structure the observations into the SOP shape below.
- Do not add steps that are not in the observations.
- For each observed step, propose one concrete control that confirms the step succeeded.
- Mark any step missing detail as "missing detail — confirm with operator."
- Do not use vague verbs ("review," "appropriately," "as needed") without testable detail.
- Owner is a role, never an individual.

INPUTS
- Process: [SYNTHETIC_PROCESS_NAME]
- Proposed owner role: [SYNTHETIC_OWNER_ROLE]
- Observed steps (each line one observable action):
[APPROVED_INPUT]
- Known owner roles in the observations: [PLACEHOLDER_OWNER]

OUTPUT FORMAT

Return a Markdown SOP draft with these sections, in this order:

1. **Purpose** — one paragraph stating why the SOP exists and what good looks like.
2. **Scope** — what the SOP covers and what it does not.
3. **Owner** — named role (not individual). Use [SYNTHETIC_OWNER_ROLE].
4. **Inputs** — what triggers the SOP and what materials it needs.
5. **Steps** — numbered, verb-led, testable. Each step is one observable action a new operator could execute without the original author present.
6. **Controls** — quality checks built into the process; one concrete control per step or step group; how the operator confirms each step succeeded.
7. **Outputs** — what the SOP produces and where it goes.
8. **Exceptions** — documented variations and what to do when the path branches.
9. **Review cadence** — when the SOP is revisited; named owner role.
10. **Open questions** — 0-3 bullets to resolve before publication.

DISCIPLINE
- If an observed step is too high-level to test ("review the report"), rewrite it as testable ("open the report; confirm the variance row exists; copy the variance number into the status doc") or mark it "missing detail — confirm with operator."
- If a control is generic ("operator confirms"), rewrite to name what is confirmed ("operator confirms the variance number matches the source row").
- If Owner appears as an individual in inputs, replace with the role from [SYNTHETIC_OWNER_ROLE].
- If a section has no input content, write "(to be defined by process owner)" — do not invent.
- Append a "Source trace" list: each step mapped to the input line that originated it.

Return the SOP draft and the source trace only.
```

## 8. Expected output

A Markdown SOP draft with ten labeled sections (Purpose, Scope, Owner, Inputs, Steps, Controls, Outputs, Exceptions, Review cadence, Open questions), followed by a "Source trace" list. Mirrors W-11 §7.

## 9. Human review checklist

The reviewer (Tom for synthetic practice; process owner for any real SOP) follows the "SOP and lessons-learned outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` and runs the post-flight checklist before publication:

- Confirm the SOP describes the actual process, not an AI-idealized version.
- Confirm steps are testable (a new operator could execute them).
- Confirm controls name what the operator confirms, not just "operator confirms."
- Confirm Owner is a role, not an individual.
- Confirm exceptions are documented, not hidden inside steps.
- Confirm review cadence is populated.

## 10. Failure modes and escalation triggers

Failure modes (mirroring W-11 §13):

- AI invents steps that look reasonable but do not match the process.
- Steps are too high-level to test.
- Controls are missing or generic.
- Owner is an individual rather than a role.
- SOP is published before the process owner has confirmed it.

Escalation triggers:

- The observations themselves are incomplete — go to the operator for a re-observation; do not iterate the AI draft.
- The process touches safety, compliance, or contract obligations — involve compliance and program leadership before publishing.
- Process observations turn out to involve Prohibited content — stop, do not use AI; reclassify.

## 11. Notes for approved-tool migration

- **Personal-preparation form (today):** Synthetic process observations, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real process observations, Employer-approved AI tool against approved scope, Strict review (testability check; control check), process-owner sign-off, full audit envelope per `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums," stored in approved venue.
- **Re-approval triggers:** SOPs covering safety, compliance, contract, or customer-facing processes; new tool environment; SOPs that automate steps. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 12. Safety precheck

Run `05_PROMPTS/P-00-safety-precheck.md` before sending the prompt in §7.

Prompt-specific precheck additions:

- Confirm observations do not reference real internal tools, real customer touch points, or real program-specific systems for personal-preparation runs.

## 13. Output critique pass (optional)

Run `05_PROMPTS/P-99-prompt-critique-and-output-qa.md` against the §7 output before any SOP draft is sent for owner sign-off. Required if the SOP will be formally adopted (Strict).

## 14. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Paired workflow card: `04_WORKFLOWS/W-11-sop-draft-generation.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0045 (also references A-0014 SOP Draft Generation Workflow in Phase 10).
- Related template: A-0057 SOP Template (Phase 10).
- Utility prompts: `05_PROMPTS/P-00-safety-precheck.md`, `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Related prompts: `P-10-lessons-learned-capture.md`.
