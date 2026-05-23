# LESSONS_LEARNED_TEMPLATE.md

## Artifact identity

- **Backlog ID:** A-0058
- **Phase:** 10 - SOP and Lessons Learned Track
- **Paired workflow card:** `04_WORKFLOWS/W-10-lessons-learned-capture.md`
- **Paired prompt card:** `05_PROMPTS/P-10-lessons-learned-capture.md`
- **Sibling templates:** `07_TEMPLATES/SOP_TEMPLATE.md`, `07_TEMPLATES/KNOWLEDGE_BASE_PATTERN.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A generic lessons-learned shape Tom fills in (with AI assistance via P-10 against synthetic or approved event notes) to capture repeatable learning while events are fresh. The template enforces the discipline that lessons are framed around process, information flow, or tool — never around individual blame — and that each lesson names a concrete recommendation with a candidate owner role.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`): Synthetic for personal practice. Employer-approved when the lesson references a real event, only inside an Employer-approved AI tool with explicit scope approval.
- **Tool environment:** ATLAS-local Markdown for the template; Personal AI tool acceptable for the drafting step when the input is Synthetic.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`): Standard for synthetic practice; Strict if the lessons-learned entry will be formally published.
- **Per-domain review pattern:** SOP and lessons-learned outputs.

## Use rules

- Frame lessons around **process, information flow, or tool** — never around an individual's performance.
- Capture facts and assumptions separately; mark which is which.
- Each lesson names: what we expected, what happened, the gap, why it matters, the recommendation, and a candidate owner role.
- Recommendations are testable: a future operator could tell whether the change actually happened.
- AI drafts the structure; the named lessons-learned reviewer (typically project leadership) approves the content. AI never names individuals in a blame frame, never publishes lessons, never alters program records.

## Lessons-learned template

```text
Lessons learned record
Record ID: [LL-NNN]
Project: [SYNTHETIC_PROJECT_NAME or APPROVED_PROJECT_LABEL]
Event period: [YYYY-MM-DD through YYYY-MM-DD]
Captured by: [Role]
Reviewer: [Role — typically project leadership]
Review status: Draft for review | Approved | Retired

1. Event summary
[One paragraph describing the event or pattern that prompted this lessons-learned entry. Frame at the process / information-flow / tool level.]

2. What we expected
- [Expected state 1]
- [Expected state 2]

3. What happened
- [Observed state 1 — fact]
- [Observed state 2 — fact]
- [Observed state 3 — assumption, marked]

4. Gap (process / information flow / tool)
- [Gap 1 — process: where the process did not anticipate this situation]
- [Gap 2 — information flow: where information that should have moved between steps did not]
- [Gap 3 — tool: where the tool's behavior or configuration contributed]

5. Why it matters
[One paragraph stating the operational consequence: what cost, schedule, quality, or governance impact resulted, framed at the project level rather than the individual level.]

6. Recommendation
- [Recommendation 1: a concrete, testable change. Candidate owner role: [Role]. Target adoption date: [YYYY-MM-DD or "next cycle"].]
- [Recommendation 2]
- [Recommendation 3]

7. Where this lesson should live
- [Pointer to the SOP, workflow, or template this lesson updates, if applicable.]
- [Pointer to the knowledge base entry this lesson creates or updates, if applicable.]

8. Approval
- Captured by [role] on [YYYY-MM-DD].
- Reviewed by [role] on [YYYY-MM-DD].
- Approved by [role] on [YYYY-MM-DD].
- Adjustments after review: [list or "none"].
```

## Quality checklist

Before sharing or publishing, confirm:

- The event summary is framed at the process / information-flow / tool level, not the individual level.
- Facts and assumptions are separated; assumptions are marked.
- The gap section names a real process, information flow, or tool — not "the team."
- The recommendation is concrete and testable; "do better next time" is not an acceptable recommendation.
- The candidate owner role is named; the actual owner is decided at review.
- The lesson points at where it should live (an SOP, a workflow card, a knowledge-base entry) so it does not become a one-off note.

## Failure modes

- Lesson names an individual or implies blame. Re-frame at the process level.
- "What happened" mixes facts and assumptions. Separate and mark.
- "Gap" reduces to "people did not communicate." Re-frame as a process or information-flow gap (e.g., "no step in the meeting workflow required action-owner confirmation before close").
- Recommendation is generic ("communicate better"). Replace with a testable change ("add an owner-confirmation step to the meeting workflow; review at next cycle").
- Lesson is captured but not pointed at where it should live; it becomes a one-off note. Add the pointer.

## Migration notes (post-clearance, post-approval)

- **Personal-preparation form (today):** Drafts against synthetic event notes; ATLAS-local Markdown; reviewer is Tom; review intensity Standard.
- **Employer-deployable form:** Same template; describes a real event; data category shifts to Employer-approved; tool environment shifts to the specific Employer-approved AI tool; review intensity shifts to Strict; the published lesson lives in the approved employer venue (knowledge base / wiki), not in ATLAS.
- **Re-approval triggers:** Any lesson moving from synthetic to real; any change of tool; any lesson that touches restricted content (real customer, real contract, real schedule). Each requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-10-lessons-learned-capture.md` (§7 output format, §9 review point).
- Paired prompt card: `05_PROMPTS/P-10-lessons-learned-capture.md`.
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Sibling templates: `07_TEMPLATES/SOP_TEMPLATE.md`, `07_TEMPLATES/KNOWLEDGE_BASE_PATTERN.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0058.
- Decision log: D-0055..D-0057 (Phase 10 set).
