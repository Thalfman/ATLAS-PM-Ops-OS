# HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md

## Purpose

Define the reusable "human review point" pattern that every ATLAS workflow and prompt inherits, and the lightweight auditability expectations that go with it.

Phase 4 (workflow library) and Phase 5 (prompt library) reference this file. They do not re-define what a human review point looks like; they cite this model and specify which review pattern applies.

This file is personal preparation material. It does not state employer audit policy. Employer audit and approval requirements take precedence over anything here.

## Why this exists

AI-assisted PM/Ops output is a draft, not a decision. The human-review-point pattern protects three things:

1. **Quality.** A named human catches AI errors before they propagate.
2. **Accountability.** Authorship of the final output stays with a person, not a tool.
3. **Auditability.** Anyone reviewing the work later can see what input was used, what the AI produced, who reviewed it, and what changed before it was used.

Without these protections, AI-assisted output is unsafe in any environment that matters.

## Three review intensities

ATLAS uses three review intensities. Pick the one that matches the output type and the data category; do not invent additional levels.

| Intensity | When to use | What the reviewer does | Recording |
|---|---|---|---|
| **Light** | Synthetic or public inputs; low-stakes practice; demos that everyone knows are fictional. | Reads the output end-to-end; corrects obvious errors; confirms safety boundary not violated. | One-line note in the relevant ATLAS file or commit message. |
| **Standard** | Tom-personal inputs; outputs that will be used in real preparation; first drafts intended for later employer review. | Reads the output critically; checks AI claims against the source; marks facts/assumptions/AI suggestions; edits and approves. | Explicit sign-off line in the output ("Reviewed by Tom YYYY-MM-DD"). |
| **Strict** | Employer-approved inputs; outputs that will be shared with stakeholders, customers, leadership, or audit systems. | Reads the source first; reads the output independently; compares against source line by line; verifies any numbers; identifies and removes overclaims; documents what changed; obtains accountable-owner approval. | Sign-off plus a record of source, tool, reviewer, accountable owner, and date inside the approved employer venue. Not in ATLAS personal preparation. |

In ATLAS personal-preparation work, Light and Standard are the only intensities actually exercised. Strict is described here so that future employer-deployable artifacts inherit the right pattern.

## Per-domain review patterns

The general pattern adapts to the domain of the output. Workflows and prompts should cite the matching pattern below.

### Status and reporting outputs

- Verify every claim has a source the reviewer can point to.
- Strip language that implies certainty the source does not support.
- Confirm forward-looking statements are clearly marked as forward-looking.
- Confirm risks are stated, not hidden.
- Standard intensity for personal practice; Strict for anything that will be shared with leadership.

### Schedule outputs (variance narratives, schedule health summaries)

- Recompute or sanity-check any numeric claim (variance percentages, durations, slack).
- Confirm the narrative matches the underlying data the reviewer can see.
- Confirm activity names and IDs match the source.
- Confirm the narrative does not over-attribute causes or commit to recovery dates the schedule does not support.
- Standard intensity for synthetic practice; Strict for any real schedule (which only happens in approved employer environments).

### Finance, EVM, and project accounting outputs

- Recompute the key numbers (CV, SV, CPI, SPI, EAC, ETC) against source data.
- Confirm units and periods match.
- Confirm narrative does not state causes the data does not justify.
- Confirm the output does not present AI inference as accounting fact.
- Standard intensity for synthetic practice; Strict for any real finance data (which only happens in approved employer environments).

### Meeting notes to action items

- Confirm every action has an owner and a date.
- Confirm the owner has actually been informed (the AI tool has not silently committed anyone).
- Confirm the action is what the owner actually agreed to, not what the AI inferred.
- Standard intensity by default. Light only for synthetic practice.

### Risk and issue triage outputs

- Confirm each entry has an owner.
- Confirm the categorization (likelihood, impact, status) matches the underlying judgment, not an AI inference.
- Confirm the mitigation or next step is actionable.
- Standard intensity by default.

### SOP and lessons-learned outputs

- Confirm the SOP describes the actual process, not an idealized AI guess.
- Confirm steps are testable (a new operator could execute them).
- Confirm lessons-learned entries do not name individuals in a way that violates fairness or policy.
- Standard intensity by default; Strict if the SOP will be formally adopted.

## Pre-flight checklist before invoking AI

A workflow or prompt invocation should not start until all of these are true.

1. The input is classified per `DATA_SENSITIVITY_DECISION_MODEL.md`.
2. The tool environment matches the input category.
3. The accountable human reviewer is named.
4. The review intensity is chosen.
5. The "good" and "bad" criteria for the output are written down (in the workflow or prompt file is enough).
6. The recording mechanism for sign-off is known.

Workflows missing any of these are not ready for use.

## Post-flight checklist before using AI output

After the AI produces output, before it is used for anything:

1. The reviewer read the output end-to-end.
2. Facts, assumptions, and AI-suggested language are distinguishable in the output.
3. Numbers were recomputed or sanity-checked.
4. Sources are cited or referenced where claims could be checked.
5. Overclaims and hallucinations were removed.
6. The reviewer signed off (per the intensity above).
7. The recording mechanism captured the sign-off.

## Auditability minimums

For employer-deployable artifacts, the minimum audit trail is:

- **Source.** What input was used.
- **Tool.** Which AI tool, in which environment.
- **Operator.** Who ran the tool.
- **Reviewer.** Who reviewed and signed off.
- **Accountable owner.** Who is responsible for the output being correct.
- **Date.** When the review happened.
- **Outcome.** Approved, edited, rejected.

For ATLAS personal preparation, the audit trail is the repo's commit history plus `09_HANDOFFS/SESSION_HANDOFF.md` and `10_DECISION_LOG/DECISION_LOG.md`.

## Common failure modes the pattern guards against

- **Plausible-but-wrong text.** The AI produces fluent output that contradicts the source. Standard and Strict reviews catch this by reading the source first.
- **Silent overclaim.** The AI states something with more certainty than the data supports. The pattern requires marking facts vs assumptions vs AI suggestions.
- **Hallucinated detail.** The AI invents a name, date, number, or system. Sanity-checks against source remove these.
- **Hidden bias.** The AI flatters the user's framing. Independent reading by the reviewer reduces this.
- **Automation creep.** The AI tool starts taking actions instead of producing drafts. The pattern forbids autonomous sending, filing, approval, or escalation.
- **Ghost authorship.** Nobody is willing to sign off because the AI "wrote it." The pattern requires a named human owner.

## How to apply this file

When a Phase 4 workflow or Phase 5 prompt is being authored:

- Cite this file by name.
- State which per-domain pattern applies.
- State the review intensity.
- Include the pre-flight and post-flight checklists in the workflow or prompt, or reference them by section.
- Define "good" and "bad" output criteria in the workflow or prompt itself.

Do not re-invent the review pattern in each workflow. Workflows are easier to maintain and safer to use when they share this single model.
