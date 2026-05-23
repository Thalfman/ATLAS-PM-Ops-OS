# SOP_TEMPLATE.md

## Artifact identity

- **Backlog ID:** A-0057
- **Phase:** 10 - SOP and Lessons Learned Track
- **Paired workflow card:** `04_WORKFLOWS/W-11-sop-draft-generation.md`
- **Paired prompt card:** `05_PROMPTS/P-11-sop-first-draft.md`
- **Sibling templates:** `07_TEMPLATES/LESSONS_LEARNED_TEMPLATE.md`, `07_TEMPLATES/KNOWLEDGE_BASE_PATTERN.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A generic SOP shape Tom fills in (with AI assistance via P-11 against synthetic or approved process descriptions) to produce a reviewable draft SOP. The template enforces the discipline that steps are testable, the owner is a role (not a person), inputs and outputs are named, and a human reviewer approves before adoption.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`): Synthetic / Public for personal practice (drafting against public PMI material or synthetic process notes). Employer-approved when the SOP describes a real employer process, only inside an Employer-approved AI tool with explicit scope approval.
- **Tool environment:** ATLAS-local Markdown for the template; Personal AI tool acceptable for the drafting step when the input is Synthetic / Public.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`): Standard for synthetic practice; Strict if the SOP will be formally adopted by a real team.
- **Per-domain review pattern:** SOP and lessons-learned outputs.

## Use rules

- Owner is a role (e.g., "Reporting Coordinator"), not a person.
- Steps are testable: a new operator could execute them.
- Each step names its input, action, and output.
- Controls (review, sign-off, audit trail) are explicit.
- The SOP itself names its revision cadence and the role that approves changes.
- AI drafts the structure; the named process owner approves the content. AI never declares an SOP adopted, never changes a real process, never alters a system of record.

## SOP template

```text
SOP: [SOP title — verb-led, scope-bounded]
SOP ID: [SOP-NNN]
Owner role: [Role, not a person]
Approver role: [Role that signs off on SOP changes]
Revision cadence: [Quarterly / annually / on trigger]
Last reviewed: [YYYY-MM-DD]
Last reviewer: [Role]
Status: Draft for review | Approved | Retired

1. Purpose
[One paragraph stating what the SOP achieves and why.]

2. Scope and audience
- In scope: [what this SOP covers]
- Out of scope: [what this SOP deliberately does not cover]
- Audience: [roles expected to use this SOP]

3. Inputs
- [Input 1: name, source, format, owner role]
- [Input 2]
- [Input 3]

4. Outputs
- [Output 1: name, destination, format, accountable role]
- [Output 2]

5. Steps
1. [Verb-led step — Input(s): X. Action: Y. Output: Z. Acceptance: a testable check the step succeeded.]
2. [Step 2]
3. [Step 3]
4. [...]

6. Controls
- Review: [who reviews what, at which step]
- Sign-off: [who signs off, on which output]
- Audit trail: [where the audit record lives]
- Exceptions: [when the SOP can be deviated from, and who authorizes the deviation]

7. Tools
- [Tool 1: name, approved for this use? yes/no/n/a]
- [Tool 2]

8. References
- [Linked SOP, policy, or governance document]
- [Linked template, workflow card, or prompt card]

9. Revision history
| Revision | Date | Reviewer | Summary of change |
|---|---:|---|---|
| 0.1 | [YYYY-MM-DD] | [Role] | Initial draft. |

10. Approval
- Drafted by [role] on [YYYY-MM-DD].
- Reviewed by [role] on [YYYY-MM-DD].
- Approved by [role] on [YYYY-MM-DD].
- Adjustments after review: [list or "none"].
```

## Quality checklist

Before sharing or adopting, confirm:

- Every step is testable; no step says "ensure quality" without naming what "quality" means.
- The owner role appears in every step that needs an owner.
- Inputs and outputs are named with sources / destinations and formats.
- Controls section names a real review pattern, not a placeholder.
- Exceptions section names who can authorize a deviation; "use judgment" is not an acceptable answer.
- The SOP fits on roughly two pages when filled in; if it grows beyond that, consider splitting.

## Failure modes

- Steps that hide multiple sub-steps inside one bullet ("validate the inputs"). Decompose.
- Owner named as a person, not a role. Re-frame as role.
- A step's acceptance criterion is missing. Add a testable check.
- Controls reduced to "review by manager." Name the role and the artifact reviewed.
- AI generates an SOP that describes a real process Tom has not been authorized to document. Stop; SOPs for real processes require the named owner's input.

## Migration notes (post-clearance, post-approval)

- **Personal-preparation form (today):** Drafts against public PMI material or synthetic process notes; ATLAS-local Markdown; reviewer is Tom; review intensity Standard.
- **Employer-deployable form:** Same template; describes a real employer process; data category shifts to Employer-approved; tool environment shifts to the specific Employer-approved AI tool; review intensity shifts to Strict for any SOP formally adopted; the SOP itself lives in the approved employer venue (document repository / wiki / SharePoint), not in ATLAS.
- **Re-approval triggers:** Any SOP moving from synthetic to real; any change of tool; any new step that touches a different data category. Each requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-11-sop-draft-generation.md` (§7 output format, §9 review point).
- Paired prompt card: `05_PROMPTS/P-11-sop-first-draft.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Sibling templates: `07_TEMPLATES/LESSONS_LEARNED_TEMPLATE.md`, `07_TEMPLATES/KNOWLEDGE_BASE_PATTERN.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0057.
- Decision log: D-0055..D-0057 (Phase 10 set).
