# SCHEDULE_VARIANCE_NARRATIVE_TEMPLATE.md

## Artifact identity

- **Backlog ID:** A-0016
- **Phase:** 8 - Microsoft Project and Schedule Integrity Track
- **Paired workflow card:** `04_WORKFLOWS/W-05-schedule-variance-narrative.md`
- **Paired prompt card:** `05_PROMPTS/P-05-schedule-variance-narrative.md`
- **Paired Phase 7 demo:** `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md`
- **Sibling template:** `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A reusable Markdown template Tom fills in (with AI assistance via P-05 against synthetic schedule deltas) to produce a defensible schedule variance narrative. The template enforces the discipline that variance numbers come from the schedule, causes are framed as observations, recovery posture cites what the schedule shows, and decisions needed are named explicitly.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real variance is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown for the template; Personal AI tool acceptable for the drafting step when the schedule delta is Synthetic. Employer-approved AI tool only with explicit scope approval.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice; Strict for any real variance narrative.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Schedule outputs.

## Use rules

- Numbers come from the schedule, not from the AI. The AI summarizes, structures, and drafts; the reviewer recomputes the headline numbers (days slipped, percent variance, paths affected) against the source.
- Causes are framed as observations ("schedule shows X starting N days after planned start") not conclusions ("Team Y delayed").
- Recovery posture cites what the schedule shows; if no recovery activities are captured in the schedule, the narrative says so rather than asserting a recovery date.
- Forward-looking statements are marked.
- Real schedule data never flows through a personal AI tool. See the Microsoft Project data-handling note in `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`.

## Variance narrative template

```text
Schedule variance narrative — [SYNTHETIC_PROJECT_NAME or APPROVED_PROJECT_LABEL]
Reporting period: [YYYY-MM-DD through YYYY-MM-DD]
Status date / data date: [YYYY-MM-DD]
Prepared by: [Tom or named human reviewer]
Reviewer: [Tom for synthetic practice; named accountable approver for real schedules]
Review status: Draft for human review

1. Variance summary (one paragraph, ~3-5 sentences)
[Headline numbers: days slipped on critical path; paths affected; whether milestone dates have moved. State whether a decision is requested. Do not bury the decision.]

2. What moved (3-5 bullets)
- [Activity ID]: [activity name]. Baseline finish [YYYY-MM-DD] -> current finish [YYYY-MM-DD] (+N days). On critical path? [yes/no].
- [Repeat per moved activity, citing IDs that match the source schedule.]

3. Apparent cause (1-3 bullets, framed as observations)
- [Observation: schedule shows X starting N days after planned start.]
- [Observation: dependency between A and B implies the delay propagates to C.]
- [Observation: constraint on D is in tension with logic, possibly contributing.]

4. Recovery posture (1-3 bullets)
- [What the schedule shows planned for recovery. If nothing is captured in the schedule, say so explicitly.]
- [Named owner for recovery actions.]
- [Forward-looking statement, clearly marked: "Forward-looking — assumes owner availability per the prior week's commitments."]

5. Decisions or inputs needed (0-3 bullets)
- [Decision needed, with target date and consequence if delayed.]
- [Input needed from a named stakeholder, with target date.]

6. Open questions or assumptions (0-3 bullets)
- [Question for the schedule owner.]
- [Assumption flagged for confirmation.]

Number trace appendix (Standard intensity required; Strict mandatory)
- [Activity ID] baseline finish [YYYY-MM-DD], current finish [YYYY-MM-DD]: variance [+N days] (recomputed by reviewer).
- [Repeat per moved activity in §2. Numbers in §1 and §2 must match this appendix; any mismatch is a finding.]

Sign-off
- Drafted by [Tom] on [YYYY-MM-DD].
- Reviewed by [Tom for synthetic practice; named accountable approver for real schedules] on [YYYY-MM-DD].
- Adjustments after review: [list or "none"].
```

## Quality checklist

Before sharing, confirm:

- Headline numbers in §1 match the number trace appendix.
- Activity IDs in §2 match the source schedule (no AI hallucinations).
- Causes in §3 are observations, not conclusions; no "Team Y is at fault" framing.
- Recovery posture in §4 either cites the schedule or explicitly says no recovery is captured; no invented recovery dates.
- Forward-looking statements are marked.
- Decisions or inputs needed in §5 are specific (named decision, target date, consequence) rather than vague ("monitor closely").
- The narrative does not exceed roughly 350 words excluding the appendix.

## Failure modes

- Numbers in the narrative do not match the appendix. Stop; fix the source of the mismatch.
- Causes asserted as conclusions ("Workstream B owner was unavailable"). Re-frame as observation ("Schedule shows Workstream B activity starting N days after planned start").
- Recovery posture cites a recovery date that is not in the schedule. Remove or re-frame as a question to the schedule owner.
- Activity IDs invented or partially correct. Verify every ID against the source.
- Real schedule content paraphrased into a personal AI tool. Stop; paraphrased restricted content is restricted content.

## Migration notes (post-clearance, post-approval)

- **Personal-preparation form (today):** Runs against synthetic workbooks (`08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`, `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md`). ATLAS-local Markdown; reviewer is Tom; review intensity Standard.
- **Employer-deployable form:** Same template; data category shifts to Employer-approved; tool environment shifts to the specific Employer-approved AI tool; review intensity shifts to Strict.
- **Re-approval triggers:** Any narrative moving from synthetic to real schedules; any change of tool; any change of audience that broadens distribution. Each requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-05-schedule-variance-narrative.md` (§7 output, §9 review point, §11 quality checks).
- Paired prompt card: `05_PROMPTS/P-05-schedule-variance-narrative.md` (drafts the narrative).
- Safety precheck: `05_PROMPTS/P-00-safety-precheck.md`.
- Critique pass: `05_PROMPTS/P-99-prompt-critique-and-output-qa.md`.
- Phase 7 demo: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md` (a worked example).
- Sibling template: `07_TEMPLATES/SCHEDULE_HEALTH_REVIEW_TEMPLATE.md` (health review, including the Microsoft Project data-handling note).
- Synthetic workbook: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0016.
