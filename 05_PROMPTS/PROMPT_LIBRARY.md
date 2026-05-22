# PROMPT_LIBRARY.md

## Prompt library purpose

This library provides Gemini-first, platform-agnostic prompts for safe PM/Ops work. Prompts must be used only with data approved for the tool being used. During personal preparation, use synthetic, fictional, public, or generic information only.

## Universal prompt safety preface

Use this safety preface when working in any AI tool:

```text
Use only the information I provide in this prompt. Do not infer employer-specific facts, program details, contract details, technical details, financial details, customer details, or internal process details. If information is missing, ask clarifying questions or mark it as unknown. Produce a draft for human review, not an official decision or final communication.
```

## Prompt 1: Weekly status report draft

```text
You are assisting with a PM/Ops weekly status report using only synthetic or approved information.

Task: Convert the notes below into a concise weekly status report for human review.

Rules:
- Do not invent facts.
- Separate confirmed items from assumptions or open questions.
- Use neutral, professional PM/Ops language.
- Highlight schedule, risk, issue, action, and decision implications.
- Include a short executive summary and a detailed action section.

Inputs:
Project/context: [synthetic or approved context]
Reporting period: [date range]
Accomplishments: [bullets]
Schedule movement: [bullets]
Risks/issues: [bullets]
Action items: [owner/date/status]
Decisions needed: [bullets]
Open questions: [bullets]

Output format:
1. Executive summary
2. Accomplishments this period
3. Schedule/status movement
4. Risks and issues
5. Decisions or support needed
6. Action item follow-up
7. Open questions and assumptions
```

## Prompt 2: Meeting notes to action items

```text
You are assisting with PM/Ops action tracking using only synthetic or approved meeting notes.

Task: Extract action items, decisions, risks, issues, dependencies, and open questions from the notes below.

Rules:
- Do not create actions that are not supported by the notes.
- If the owner or due date is missing, mark it as TBD.
- Use neutral wording.
- Do not include sensitive details unless the tool is approved for that data.
- Produce a draft for human review.

Meeting notes:
[paste synthetic or approved notes]

Output format:
| Type | Item | Owner | Due date | Status | Dependency | Follow-up needed | Confidence |
|---|---|---|---|---|---|---|---|

After the table, list:
- Decisions captured
- Risks/issues surfaced
- Clarifying questions for the meeting owner
```

## Prompt 3: Action item aging review

```text
You are assisting with action item aging analysis using only synthetic or approved action tracker data.

Task: Review the action list and identify items that are overdue, stale, blocked, ambiguous, duplicated, or missing owner/due date information.

Rules:
- Do not blame owners.
- Use neutral PM/Ops follow-up language.
- Do not escalate anything automatically.
- Mark uncertain items for human review.

Action tracker:
[paste synthetic or approved table]

Output format:
1. Aging summary
2. High-priority follow-up list
3. Missing owner/date list
4. Blocked or dependency-heavy items
5. Suggested neutral follow-up messages
6. Items requiring human review before action
```

## Prompt 4: Microsoft Project schedule health review

```text
You are assisting with schedule health review using only synthetic or approved schedule information.

Task: Review the schedule fields below and flag potential schedule hygiene issues.

Rules:
- Do not change dates or logic.
- Do not override scheduler or SME judgment.
- Do not infer technical causes.
- Identify questions a PM/Ops person should ask.
- Produce observations for human review.

Schedule data:
[paste synthetic or approved task list with fields such as ID, task, start, finish, predecessor, successor, baseline, percent complete, constraint, owner]

Output format:
| Observation | Evidence | Why it matters | Suggested question | Severity | Human reviewer |
|---|---|---|---|---|---|

Also provide:
- Top schedule integrity themes
- Possible variance narrative elements
- Items that require scheduler/SME validation
```

## Prompt 5: Schedule variance narrative support

```text
You are assisting with a schedule variance narrative using only synthetic or approved schedule information.

Task: Draft a concise variance explanation from the facts provided.

Rules:
- Do not invent root causes.
- If cause is unknown, say it is unknown and list questions.
- Separate cause, impact, corrective action, and next verification step.
- Use professional, audit-friendly language.

Inputs:
Baseline milestone/date: [value]
Current milestone/date: [value]
Variance amount: [value]
Known cause(s): [bullets]
Impact: [bullets]
Corrective action: [bullets]
Owner: [role/name if approved]
Next review date: [date]

Output format:
1. One-sentence variance summary
2. Cause
3. Impact
4. Corrective action
5. Remaining uncertainty
6. Next verification step
```

## Prompt 6: EVM variance explanation support

```text
You are assisting with an EVM variance explanation using only synthetic or approved EVM information.

Task: Convert the inputs into a cause-impact-corrective action narrative for human review.

Rules:
- Do not invent financial causes.
- Do not make accounting determinations.
- Do not use contract-specific language unless provided and approved.
- Mark missing information clearly.

Inputs:
Metric(s): [CPI/SPI/CV/SV or synthetic equivalent]
Variance: [value]
Period: [date range]
Known driver(s): [bullets]
Impact: [bullets]
Corrective action: [bullets]
Owner: [role/name if approved]
Open questions: [bullets]

Output format:
1. Draft variance narrative
2. Evidence used
3. Missing evidence
4. Corrective action clarity check
5. Questions for project controls/finance review
```

## Prompt 7: Risk register cleanup

```text
You are assisting with risk register cleanup using only synthetic or approved risk data.

Task: Review the risk entries and improve clarity without changing the underlying meaning.

Rules:
- Do not invent probability, impact, owner, mitigation, or trigger values.
- If a field is missing, mark it as missing.
- Use condition-consequence wording where possible.
- Produce a draft for risk owner review.

Risk entries:
[paste synthetic or approved entries]

Output format:
| Original risk | Cleaned risk statement | Trigger | Consequence | Mitigation | Owner | Missing fields | Review questions |
|---|---|---|---|---|---|---|---|
```

## Prompt 8: Project accounting reconciliation narrative

```text
You are assisting with a project accounting reconciliation narrative using only synthetic or approved data.

Task: Structure the discrepancy information into an investigation narrative.

Rules:
- Do not make accounting conclusions.
- Do not invent causes.
- Separate observed mismatch, possible explanations, evidence needed, and next actions.
- Use neutral language suitable for finance/project controls review.

Inputs:
Observed mismatch: [description]
Source A: [synthetic or approved source]
Source B: [synthetic or approved source]
Amount/date/category involved: [values]
Known timing issues: [bullets]
Known coding issues: [bullets]
Open questions: [bullets]

Output format:
1. Reconciliation summary
2. Observed mismatch
3. Possible explanations to validate
4. Evidence needed
5. Recommended next actions
6. Items for finance/project controls review
```

## Prompt 9: SOP draft generation

```text
You are assisting with SOP drafting using only synthetic or approved process notes.

Task: Convert the process notes into a reviewable SOP draft.

Rules:
- Do not create policy.
- Do not invent approvals or compliance requirements.
- Mark unknown ownership, systems, and controls as TBD.
- Write for human review and process-owner approval.

Process notes:
[paste synthetic or approved notes]

Output format:
1. SOP title
2. Purpose
3. Scope
4. Roles and responsibilities
5. Inputs
6. Procedure steps
7. Outputs
8. Controls/checks
9. Exceptions
10. Open questions for process owner
```

## Prompt 10: Executive brief draft

```text
You are assisting with an executive brief using only synthetic or approved information.

Task: Create a concise leadership-ready brief.

Rules:
- Do not overstate certainty.
- Do not include technical detail unless necessary for the decision.
- Make decisions/support needed clear.
- Keep tone factual, calm, and accountable.

Inputs:
Topic: [topic]
Current state: [bullets]
Progress: [bullets]
Risks/issues: [bullets]
Decisions needed: [bullets]
Recommended next step: [bullets]
Unknowns: [bullets]

Output format:
1. Bottom line
2. Current state
3. What changed
4. Risk/issue implications
5. Decision or support needed
6. Next step
```
