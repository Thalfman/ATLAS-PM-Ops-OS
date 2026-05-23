# W-02-meeting-notes-to-actions - Meeting notes to action items

## Workflow identity

- **ID:** W-02
- **Backlog ID:** A-0009
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Meeting notes to action items.

## 2. PM/Ops problem addressed

Meeting outcomes routinely remain buried in narrative notes and never become trackable owner/date/action records. Actions get implied rather than confirmed; ownership and due dates are inferred rather than agreed; the next meeting starts without a clear status on the last one.

## 3. Intended outcome

A short, deduplicated action table extracted from a single meeting's notes, with every row carrying a named owner, a real due date, a one-line action description, a dependency flag if relevant, and a status field. Each row reflects what an attendee actually agreed to, not what an AI inferred.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice; Tom-personal for Tom's own notes from public or non-restricted meetings.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for synthetic and Tom-personal inputs. Employer-approved AI tool when the meeting itself is employer business and the tool is approved for that content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard by default. Light only for clearly fictional practice.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Meeting notes to action items.

## 5. Safe inputs

- Fictional meeting notes authored by Tom for practice.
- Tom's own notes from public or non-restricted meetings (e.g., training sessions, vendor briefings, public conferences).
- Generic example notes from training material.

## 6. Prohibited inputs

- Real internal meeting notes from employer business unless the meeting itself and the tool are both approved for the content.
- Notes that reference real program names, contract details, customer details, financials, or internal technical content without explicit approval.
- Notes that paraphrase restricted briefings (paraphrased restricted content is restricted content).

## 7. Output format

A Markdown table with the following columns, one row per agreed action:

| # | Owner | Action (verb-led, one line) | Due date | Dependency | Status | Source line |
|---|---|---|---|---|---|---|

Plus, below the table:

- **Open questions** (0-3 bullets) - anything the notes could not resolve.
- **Decisions made** (0-3 bullets) - decisions the meeting captured but that are not themselves actions.
- **Source range** - the section of the input notes the table was derived from.

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with synthetic or Tom-personal notes. Same workflow runs unchanged in an Employer-approved AI tool against approved meeting content; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom. For any action with an external owner, the owner themselves is the accountable confirmer. Review intensity from §4 applies. Reviewer follows the "Meeting notes to action items" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: confirm every action has an owner and a date, confirm the owner has actually been informed (AI has not silently committed anyone), confirm the action is what the owner actually agreed to and not what the AI inferred.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Paste the meeting notes.** Provide the raw notes in full. Do not summarize them before extraction.
4. **Ask AI to extract, not infer.** Prompt the AI to produce the §7 table containing only actions explicitly named or clearly agreed in the source. Inferred or implied actions go into the "Open questions" bullet list, not the table.
5. **Verify each row against the source line.** Open the source line referenced in the last column. Confirm the row reflects what was actually said and agreed. Edit or delete rows that fail.
6. **Confirm with the owner where needed.** Any action with an external owner gets a confirmation message before it appears in any tracking system; Tom drafts the message, the human owner agrees.
7. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
8. **Record sign-off.** Standard intensity: sign-off line in the document ("Reviewed by Tom YYYY-MM-DD"). For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every row has a named owner and a real due date.
- Every row points back to a source line in the notes.
- Actions are verb-led and one line.
- Open questions and decisions are separated from actions.
- Duplicates from the meeting are merged.

Red flags:
- A row whose owner is "team" or "TBD."
- A row with no source line.
- Inferred actions presented as agreed actions.
- Due dates the AI invented to fill a column.
- Sensitive details (program names, contract IDs) inside the table that should not be there.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": source notes, tool, operator, reviewer, accountable owner, date, outcome, storage location.

## 13. Failure modes and escalation triggers

Failure modes:
- AI invents an owner the notes do not name.
- AI invents a due date to satisfy the column.
- AI silently commits a person to an action they did not agree to.
- AI compresses a disagreement into a single action that hides the disagreement.
- Reviewer accepts the table without opening the source notes.

Escalation triggers (stop iterating the AI draft, go to a human):
- The notes themselves are ambiguous about who agreed to what - go to the attendees.
- An action would require Tom or another person to commit beyond their authority - go to manager.
- The notes turn out to contain restricted content - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Fictional or Tom-personal notes, Personal AI tool, Standard review, sign-off line in the output.
- **Employer-deployable form (after approval):** Real meeting notes from approved-content meetings, Employer-approved AI tool, Strict review, full audit envelope, owner-confirmation step per action before the row enters any official tracker.
- **Re-approval triggers:** New meeting category (e.g., contract-bearing meetings), new tool environment, expanded data scope. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0009.
- Paired Phase 5 prompt: A-0040 Meeting Notes to Actions Prompt (TBD in Phase 5).
- Related workflows: W-01 (weekly status report), W-03 (action item aging).
