# W-03-action-item-aging - Action item aging and owner follow-up

## Workflow identity

- **ID:** W-03
- **Backlog ID:** A-0010
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Action item aging and owner follow-up.

## 2. PM/Ops problem addressed

Open action items accumulate silently. Stale actions erode credibility, hide schedule and readiness risk, and create friction with owners who feel ambushed by late follow-up. Pure mechanical aging reports (overdue by N days) without context produce blame-tinged communication; pure prose summaries hide which actions actually need to move.

## 3. Intended outcome

An aging summary that names every stale, blocked, ambiguous, duplicate, or dependency-heavy action in the tracker, plus a neutral, owner-tagged follow-up draft Tom can adapt before contacting the owner. Tom (not the AI) decides whether to escalate.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for Tom's own action tracker entries with no employer-restricted content.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for synthetic and Tom-personal inputs. Employer-approved AI tool when the action tracker is employer business and the tool is approved.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for personal preparation. Strict for any follow-up message that will leave Tom's hands.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Meeting notes to action items (closest match; same accountability discipline applies to follow-up).

## 5. Safe inputs

- Synthetic action tracker with fictional owners, dates, and statuses.
- Tom's own personal action notes from public meetings or his own preparation.
- Aging actions in a generic, fictional project context for practice.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real employer action trackers, real owner names, real internal due dates, or real internal program references unless the tracker and tool are both approved.
- Action items that reveal restricted program structure, customer identities, contract obligations, or financial commitments.
- Aging analysis on prohibited-data trackers - no AI use; revert to manual review.

## 7. Output format

A two-part Markdown output:

**Part 1 - Aging summary table**

| # | Action | Owner | Original due date | Days overdue | Blocker / dependency | Recommended next step |
|---|---|---|---|---|---|---|

**Part 2 - Follow-up drafts (neutral tone)**

For each row that warrants follow-up, a 3-5 sentence message draft addressed to the owner. Each draft:

- Names the action and the original due date.
- Acknowledges the owner's context.
- Asks a single clear question or proposes a single next step.
- Avoids "you missed" or "you're late" language.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic or Tom-personal input. Same workflow runs unchanged in an Employer-approved AI tool against an approved tracker; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. For any follow-up that will actually be sent, the owner is the accountable confirmer (Tom does not commit them silently). Review intensity from §4 applies. Reviewer follows the "Meeting notes to action items" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: every action has an owner and a date, the owner has not been silently committed, the action is what the owner actually agreed to.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide the tracker snapshot.** Paste the action tracker as a table, including original due dates and current status.
4. **Ask AI to classify aging.** Prompt the AI to label each open action with one of: overdue, blocked, ambiguous, duplicate, dependency-heavy, or on-track. AI may not invent missing data; missing data is labeled "missing field."
5. **Ask AI to draft follow-ups in neutral tone.** One short message per row that needs follow-up. Forbid blame language ("you missed"), forbid escalation threats, forbid presumptions about owner intent.
6. **Read each draft against the owner's likely context.** Edit. Remove anything that could be received as blame.
7. **Decide escalation.** Tom (not the AI) decides whether any row warrants escalation to a manager. AI may suggest "consider escalation" but may not send anything.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the document ("Reviewed by Tom YYYY-MM-DD"). For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every row carries an aging classification with a reason.
- Follow-up drafts are short, neutral, and addressed to a named owner.
- "Missing field" appears wherever the tracker did not have data, instead of an AI guess.
- Drafts ask one question or propose one next step.
- No row recommends escalation without a stated trigger.

Red flags:
- Aging classification that does not match the data (e.g., "overdue" when no due date exists).
- Follow-up drafts that read as accusatory.
- AI volunteering to send messages or take action on Tom's behalf.
- Drafts that reference unrelated actions or pile on history.
- Owners assigned to actions that do not appear in the tracker.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": tracker snapshot, tool, operator, reviewer, accountable owner, date, outcome (which follow-ups sent), storage location of the sent messages.

## 13. Failure modes and escalation triggers

Failure modes:
- AI flags an action overdue when its due date was never set.
- Follow-up drafts that imply ownership Tom does not have.
- AI recommends escalation based on aging alone, without context.
- Drafts that disclose restricted information to an external owner.
- Reviewer accepts the table without checking the owner field.

Escalation triggers (stop iterating the AI draft, go to a human):
- An aging action turns out to be in someone else's tracker - go to the actual owner.
- A blocker is structural (resource, authority, dependency) - go to manager.
- Repeated overdue from the same owner with no response - go to manager with a neutral framing, not via the AI tool.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic or Tom-personal tracker, Personal AI tool, Standard review, sign-off line in the output. Tom drafts; Tom decides; nothing leaves the tool.
- **Employer-deployable form (after approval):** Approved-content tracker, Employer-approved AI tool against approved scope, Strict review, owner-confirmation step before any follow-up is sent through an approved channel, full audit envelope.
- **Re-approval triggers:** New tracker scope, new owner population, new channel for follow-ups, automated sending of any kind. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0010.
- Paired Phase 5 prompt: P-03 Action Aging Summary (`05_PROMPTS/P-03-action-aging-summary.md`, backlog A-0041).
- Related workflows: W-02 (meeting notes to actions), W-08 (issue and discrepancy triage).
