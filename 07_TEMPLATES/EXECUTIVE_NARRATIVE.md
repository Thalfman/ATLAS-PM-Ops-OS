# EXECUTIVE_NARRATIVE.md

## Artifact identity

- **Backlog ID:** A-0006
- **Phase:** 6 - First-Week Readiness Kit
- **Operating workflow:** `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`
- **Kit index:** `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`
- **Paired Phase 4 workflow:** `04_WORKFLOWS/W-12-executive-brief-generation.md`
- **Paired Phase 5 prompt:** `05_PROMPTS/P-12-executive-brief-drafting.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

This template helps convert PM/Ops information into a clear leadership-ready narrative. It is suitable for synthetic practice during clearance-limited onboarding and can later be adapted inside approved employer systems with approved data, per `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md` (D-0026) and the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic-only for personal practice. The narrative becomes Employer-approved only inside an approved tool with explicit approval for that data category.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown for the template; Personal AI tool acceptable for drafting against Synthetic inputs only. Employer-approved AI tool for any narrative against employer data, once approved.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for personal practice with named human reviewer; Strict for any narrative shared with leadership, customers, or audit systems (only inside the approved employer venue).
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs.

## PM/Ops + AI integration positioning

Tom's posture for an executive narrative is straightforward: AI organizes information and drafts language; Tom owns the narrative and the decision. The reviewer sees a structured draft, not an autonomous output. Forward-looking statements are marked. Facts, assumptions, and unknowns are separated. The bottom line names what leadership action is needed without burying it.

This positioning carries forward into employer-deployable use once approvals exist. The template's structure does not change; the data category and tool environment do.

## Use rules

- Do not use real employer data in personal tools.
- Do not invent causes, impacts, dates, owners, financials, or commitments.
- Separate confirmed facts from assumptions.
- Mark forward-looking statements explicitly as forward-looking.
- Keep the tone calm, accountable, and decision-oriented.
- Human review is required before any official use; the named human reviewer signs off per the review intensity above.
- For AI-assisted drafting against synthetic input, use `05_PROMPTS/P-12-executive-brief-drafting.md` and the post-flight critique in `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.

## Executive narrative template

```text
Subject: [Program/Project/Topic - use only approved naming; synthetic placeholder for personal practice]
Reporting period: [Date range]
Prepared by: [Name/role]
Reviewer: [Named human reviewer]
Review status: Draft for human review

Bottom line:
[One to three sentences that state current status, key movement, and whether leadership action is needed.]

Current state:
- [Confirmed fact 1]
- [Confirmed fact 2]
- [Confirmed fact 3]

What changed since last update:
- [Change 1]
- [Change 2]
- [Change 3]

Schedule / execution implications:
- [Schedule implication, if known]
- [Dependency implication, if known]
- [Unknowns or validation needed]

Cost / resource / accounting implications:
- [Cost/resource implication, if known]
- [Reconciliation item, if any]
- [Unknowns or validation needed]

Risks and issues:
- Risk/Issue: [Description]
  - Impact: [Impact]
  - Owner: [Owner or TBD]
  - Next action: [Action]

Decisions or support needed:
- [Decision/support item]
- Due by: [Date or TBD]
- Consequence if delayed: [Impact or unknown]

Forward-looking statements (marked):
- [Forecast or projection 1 - marked as forward-looking]
- [Forecast or projection 2 - marked as forward-looking]

Next steps:
- [Action] — Owner: [Owner] — Due: [Date]
- [Action] — Owner: [Owner] — Due: [Date]

Open questions / assumptions:
- [Question or assumption]
- [Question or assumption]

Sign-off:
- Drafted by [Tom] on [YYYY-MM-DD].
- Reviewed by [Named human reviewer] on [YYYY-MM-DD].
- Adjustments after review: [list or "none"].
```

## Narrative quality checklist

Before sharing, confirm:

- The bottom line is clear and names leadership action explicitly when needed.
- The narrative does not bury the decision needed.
- Facts, assumptions, and unknowns are separated.
- Forward-looking statements are clearly marked.
- No unsupported root cause is stated as fact.
- No sensitive data is included in an unapproved tool or channel.
- Owners and dates are verified or marked TBD.
- The tone is neutral and non-defensive.
- The reviewer's sign-off line is filled in before any external use.

## Failure modes

- Bottom-line overstatement: claiming progress, recovery, or stability that the source does not support.
- Cause attribution: assigning a root cause the data does not establish.
- Owner invention: naming an owner who has not actually agreed to the action.
- Forward-looking mismarking: forecasts presented as current state.
- Synthetic-to-real drift: a synthetic practice narrative starts to look like a real-program narrative through accumulated specificity. If it could be mistaken for a real program, re-anonymize.

## Migration notes (post-clearance, post-approval)

- **Personal-preparation form (today):** Synthetic placeholders only; ATLAS-local Markdown; named human reviewer is Tom; review intensity Standard.
- **Employer-deployable form:** Same template structure; data category shifts to Employer-approved (matched to the tool's approved scope); tool environment shifts to the specific Employer-approved AI tool; review intensity shifts to Strict for any narrative leaving the team; reviewer named per employer policy.
- **Re-approval triggers:** Any narrative moving from synthetic practice to employer data; any change of tool; any change of audience that broadens distribution. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## Cross-references

- Operating workflow: `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`.
- Paired workflow card (executive brief): `04_WORKFLOWS/W-12-executive-brief-generation.md`.
- Paired prompt card (AI-drafting step): `05_PROMPTS/P-12-executive-brief-drafting.md`.
- Output critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Kit index: `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0006.
