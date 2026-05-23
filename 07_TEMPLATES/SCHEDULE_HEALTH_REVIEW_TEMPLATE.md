# SCHEDULE_HEALTH_REVIEW_TEMPLATE.md

## Artifact identity

- **Backlog ID:** A-0015
- **Phase:** 8 - Microsoft Project and Schedule Integrity Track
- **Paired workflow card:** `04_WORKFLOWS/W-04-schedule-health-review.md`
- **Paired Phase 7 demo:** `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md` (variance side) and the new `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md` (richer schedule fidelity for health review)
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A generic schedule-health review checklist usable against any synthetic Microsoft-Project-like schedule. Pre-onboarding it runs against synthetic workbooks (`08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`). Post-clearance it can be adapted inside an approved employer environment for real schedules; the structure does not change, the data category and tool environment do.

The template is intentionally tool-agnostic. It does not assume `.mpp` files in any personal tool. The "Microsoft Project data-handling note" section names the boundary explicitly.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real schedules are Employer-approved at best; never input into a personal AI tool.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown for the template; Personal AI tool acceptable when the schedule input is Synthetic. Employer-approved AI tool only with explicit scope approval for real schedule data.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice; Strict for any real schedule review.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Schedule outputs.

## Use posture

- Reviewer is a PM/Ops voice on schedule integrity, not a technical estimator. Durations, dependencies, and recovery dates remain with the named owners.
- Findings are framed as observations ("schedule shows X") not conclusions ("Team Y caused Z").
- AI can summarize, structure, and propose questions. AI does not declare official schedule status, change dates, change dependencies, or approve baselines.
- Real Microsoft Project files (`.mpp`) and internal schedule exports are never uploaded to a personal or unapproved AI tool. See "Microsoft Project data-handling note" below.

## Schedule health checklist

Each item is yes / no / not visible. A "not visible" answer is itself a finding worth raising.

### A. Baseline awareness

1. Is there a current baseline saved against the schedule?
2. Is the baseline visible in the working file or only in a separate export?
3. Has the baseline been re-set since the most recent re-plan? If so, when and by whom?
4. Are baseline-vs-current variances reported alongside the schedule, or are they computed ad hoc?

### B. Milestone integrity

5. Does every milestone have a zero-duration marker and a clear ownership label?
6. Are milestone titles consistent with the project's reporting vocabulary (no internal jargon that a stakeholder would not recognize)?
7. Are there duplicate or near-duplicate milestones representing the same event under different names?
8. Are sequencing milestones (kickoff, gate review, baseline approval, closeout) present and dated?

### C. Logic and dependency review

9. Is every task linked to at least one predecessor and at least one successor (orphan check)?
10. Are dependency types (FS, SS, FF, SF) appropriate, or is everything FS by default?
11. Are circular dependencies present? (Most tools report these; verify the warnings list is empty.)
12. Are dangling tasks present (tasks with no successor) that should logically feed a downstream activity?

### D. Constraints

13. Are constraint types other than ASAP / ALAP unusually frequent (Must Start On, Must Finish On, Start No Earlier Than)?
14. Is the constraint count justified by external commitments, or is it accumulated from older planning?
15. Do any constraints appear to be in tension with the logic (e.g., a Must Finish On date earlier than the predecessor's finish)?

### E. Lags and leads

16. Are negative lags (lead time) present? If so, are they intentional or an artifact?
17. Are excessive positive lags (>5 working days) used as a substitute for a real task that should be on the schedule?
18. Are lags applied at the task level or hidden inside dependency relationships?

### F. Critical path

19. Is the current critical path visible and labeled?
20. Has the critical path changed since the last review? If so, what was the previous path and what changed?
21. Is the critical path realistic (i.e., the slowest path through real work) or is it driven by an unrelated constraint or filter setting?
22. Are near-critical paths (within N days of the critical path) identified, and how many?

### G. Float and slack

23. Is total slack interpreted with awareness that it can be misleading when constraints are active?
24. Are tasks with negative total slack flagged and explained (recovery posture)?
25. Are large positive slack values examined for whether they reflect genuine flexibility or a missing dependency?

### H. Resource and owner clarity (if visible and approved)

26. Does every task have a named owner (role or person)?
27. Are over-allocated resources flagged?
28. Are owner assignments consistent with the work-breakdown structure?

### I. Status date and data date awareness

29. Is the status date current (within the last reporting cycle)?
30. Has progress been entered against the status date, or does it appear to have been moved without progress capture?
31. Are tasks past their due date but not marked complete or in progress?

### J. Late starts and late finishes

32. Are tasks with current start later than baseline start identified?
33. Are tasks with current finish later than baseline finish identified, and is the variance categorized (days, percent, critical-path impact)?
34. Are forecast finishes inconsistent with current progress (e.g., a task at 0% complete with a forecast finish in the next 24 hours)?

### K. Forecast vs baseline variance

35. Is variance reported per-task and rolled up per-workstream / per-milestone?
36. Is the variance trended over time (this week vs last week) or only reported as a snapshot?
37. Are variance causes captured separately from the variance numbers (so observations are not blended with conclusions)?

### L. Review limitations when data is incomplete

38. Note any sections the reviewer could not complete because of missing data, missing access, or restricted views.
39. Mark any conclusions that depend on data not seen — those are tentative until confirmed by the owner.
40. Record what the reviewer did not change: PM/Ops review of synthetic or approved data does not change baselines, dates, dependencies, or assignments.

## Microsoft Project data-handling note

Real Microsoft Project files (`.mpp`) and exports from any employer scheduling tool are sensitive content. The following rules are binding for ATLAS personal-preparation use; employer policy takes precedence whenever it differs.

- Do not upload `.mpp` files, real schedule exports, real CSV / XLSX schedule extracts, or screenshots of real schedules to any personal AI tool.
- Do not paraphrase real schedule content into a personal note for AI summarization. Paraphrased restricted content is restricted content (`06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Things that look safer than they are").
- Do not let filenames, milestone names, customer-coded WBS labels, or sponsor names leak through metadata or screenshots.
- This template runs against synthetic workbooks (`08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`) for personal practice. For real schedules, the same template runs only inside an Employer-approved AI tool after re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.
- If a real schedule review is requested but the data path is not approved, the right move is to ask for the approval path before the review, not to "just look at it quickly" in a personal tool.

## Output shape (when the template is filled in)

```text
Schedule health review — [SYNTHETIC_PROJECT_NAME or APPROVED_PROJECT_LABEL]
Schedule snapshot date: [YYYY-MM-DD]
Reviewer: [Tom or named human reviewer]
Data category: [Synthetic | Employer-approved] (and the approval reference if Employer-approved)

Findings by section (A..L):
- A. Baseline awareness: [yes/no/not visible per item, with one-line observation]
- B. Milestone integrity: ...
- (continue through L)

Top findings (3-5 most consequential observations):
- [Finding 1, framed as observation]
- [Finding 2]
- [Finding 3]

Questions for the schedule owner:
- [Question 1]
- [Question 2]

Limitations of this review:
- [What the reviewer could not see, what was tentative]

Sign-off:
- Drafted by [Tom] on [YYYY-MM-DD].
- Reviewed by [Tom for synthetic practice; named accountable approver for real schedules] on [YYYY-MM-DD].
- Adjustments after review: [list or "none"].
```

## Failure modes

- Reviewer drifts into technical estimating ("the duration should be 5 days, not 7"). PM/Ops review observes; owners decide durations.
- Findings are stated as conclusions ("Team Y is late"). Re-frame as observations ("Schedule shows Task X starting N days after planned start").
- Real schedule content gets paraphrased into a personal note for AI summarization. Stop; the paraphrase is still restricted content.
- AI is asked to "recommend a recovery plan." AI may surface candidate questions or restate observed slack; it does not recommend recovery and does not commit dates.
- Critical path is interpreted from a filtered or sorted view that is not actually the critical path. Confirm against the tool's own critical-path indicator.

## Migration notes (post-clearance, post-approval)

- **Personal-preparation form (today):** Runs against `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md` or any synthetic schedule. ATLAS-local Markdown; reviewer is Tom; review intensity Standard.
- **Employer-deployable form:** Same checklist; data category shifts to Employer-approved (matched to the tool's approved scope); tool environment shifts to the specific Employer-approved AI tool; review intensity shifts to Strict; reviewer named per employer policy.
- **Re-approval triggers:** Any review moving from synthetic practice to real schedules; any change of tool; any change of audience that broadens distribution. Each requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## Cross-references

- Paired workflow card: `04_WORKFLOWS/W-04-schedule-health-review.md`.
- Sibling template: `07_TEMPLATES/SCHEDULE_VARIANCE_NARRATIVE_TEMPLATE.md`.
- Synthetic workbook this template runs against: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_WORKBOOK.md`.
- Phase 7 demo on the variance side: `08_SYNTHETIC_DEMOS/SYNTHETIC_SCHEDULE_VARIANCE_DEMO.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_TOOL_APPROVAL_STRATEGY.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0015.
- Decision log: D-0049..D-0051 (Phase 8 set).
