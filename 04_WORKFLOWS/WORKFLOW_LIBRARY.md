# WORKFLOW_LIBRARY.md

## Library purpose

This file collects reusable PM/Ops workflows that can be performed manually, supported by Gemini Enterprise, and later migrated to approved enterprise systems. Each workflow should improve project integrity, reporting quality, schedule/accounting reconciliation, discrepancy resolution, action tracking, lessons learned, SOP quality, or executive communication.

## Universal workflow rules

1. Use only approved tools for employer data.
2. Use only synthetic/generic data in personal preparation.
3. Keep a human accountable for review and decisions.
4. Ask AI to structure, compare, summarize, draft, or flag inconsistencies; do not ask AI to make official commitments.
5. Preserve audit trails: input source, date, human reviewer, output destination, and unresolved assumptions.
6. Avoid black-box automation until the manual process is accepted and stable.

## Standard workflow card format

Each workflow should use this structure:

```text
Workflow name:
PM/Ops problem:
Safe inputs:
Prohibited inputs:
AI support role:
Human review role:
Output:
Cadence:
Audit trail:
Migration path:
```

## Starter workflow cards

### 1. AI-assisted weekly status report

**PM/Ops problem:** Weekly reporting can become inconsistent, overly technical, or disconnected from schedule, action, risk, and financial realities.

**Safe inputs for personal prep:** Synthetic milestone list, fictional accomplishments, fictional blockers, generic risk examples, and generic next-step items.

**Prohibited inputs in personal tools:** Real employer status reports, internal schedules, contract details, customer details, financials, technical content, or nonpublic program names.

**AI support role:** Help structure a draft into executive-readable sections: accomplishments, schedule movement, risks/issues, decisions needed, and next steps.

**Human review role:** Verify facts, remove unsupported claims, calibrate tone, and approve final wording.

**Output:** Human-reviewed weekly status narrative.

**Cadence:** Weekly or aligned to existing reporting rhythm.

**Audit trail:** Source list, drafter, reviewer, date, final destination.

**Migration path:** Start as Gemini-assisted drafting in approved docs; later integrate with approved reporting systems if allowed.

### 2. AI-assisted meeting notes to action items

**PM/Ops problem:** Meeting outcomes often remain buried in notes instead of becoming clear owner/date/action records.

**Safe inputs for personal prep:** Fictional meeting notes or Tom-created generic examples.

**AI support role:** Extract action items, owners, due dates, dependencies, risks, open questions, and decisions from notes.

**Human review role:** Confirm each action is real, assign correct owner, validate due date, and remove sensitive details.

**Output:** Action item table with owner, due date, status, aging, dependency, and follow-up language.

**Cadence:** After recurring meetings.

**Migration path:** Approved Docs/Sheets first; later approved action tracker or PMIS integration.

### 3. AI-assisted action item aging and follow-up

**PM/Ops problem:** Aging actions erode credibility and create hidden schedule or readiness risk.

**Safe inputs for personal prep:** Synthetic action tracker with fictional owners and dates.

**AI support role:** Identify overdue, blocked, ambiguous, duplicate, or dependency-heavy actions. Draft neutral follow-up language.

**Human review role:** Validate ownership and context. Avoid blame language. Confirm whether escalation is appropriate.

**Output:** Aging summary and owner follow-up draft.

**Cadence:** Twice weekly or before staff meetings.

### 4. AI-assisted schedule health review

**PM/Ops problem:** Schedules may contain logic gaps, stale dates, unclear dependencies, missing baselines, or variance narratives that are difficult to explain.

**Safe inputs for personal prep:** Synthetic task list, fictional dependencies, generic schedule fields.

**AI support role:** Flag likely schedule hygiene issues, ask clarifying questions, and help draft variance narratives.

**Human review role:** Validate with scheduler/SMEs. Do not override technical estimates.

**Output:** Schedule health observation list and narrative draft.

**Migration path:** Microsoft Project export reviewed only inside approved environment; Gemini or other AI only if approved for that data.

### 5. AI-assisted EVM variance explanation support

**PM/Ops problem:** Variance explanations can be vague, inconsistent, or disconnected from corrective action.

**Safe inputs for personal prep:** Synthetic CPI/SPI examples, fictional variance drivers, generic corrective actions.

**AI support role:** Help structure cause-impact-corrective action narratives and identify missing explanation elements.

**Human review role:** Verify actual numbers, contractual language, and finance/program controls. Do not let AI invent causes.

**Output:** Draft variance explanation for review.

### 6. AI-assisted risk register cleanup

**PM/Ops problem:** Risks often lack clear condition, consequence, trigger, owner, mitigation, or response status.

**Safe inputs for personal prep:** Fictional risk examples.

**AI support role:** Rewrite vague risk statements into condition-consequence form and flag missing fields.

**Human review role:** Confirm risk validity, owner, probability/impact, and response plan.

**Output:** Cleaned risk register entries ready for human review.

### 7. AI-assisted project accounting reconciliation narrative

**PM/Ops problem:** Schedule, labor, accounting, and reporting views may not align, and the narrative can become unclear.

**Safe inputs for personal prep:** Synthetic cost categories, fictional mismatches, generic period close examples.

**AI support role:** Structure discrepancy hypotheses, investigation steps, and neutral reconciliation narrative.

**Human review role:** Confirm with finance/project controls. Do not use AI to make accounting determinations.

**Output:** Investigation summary and reconciliation narrative draft.

### 8. AI-assisted lessons learned capture

**PM/Ops problem:** Lessons are often captured too late or at too high a level to change future behavior.

**Safe inputs for personal prep:** Fictional project event summaries.

**AI support role:** Convert event notes into lesson, trigger, impact, root cause, prevention, and SOP update candidates.

**Human review role:** Validate accuracy, remove sensitive details, and approve reuse.

**Output:** Lessons learned record and SOP update recommendation.
