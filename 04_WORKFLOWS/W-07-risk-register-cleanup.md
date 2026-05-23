# W-07-risk-register-cleanup - Risk register cleanup

## Workflow identity

- **ID:** W-07
- **Backlog ID:** A-0011
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Risk register cleanup.

## 2. PM/Ops problem addressed

Risk registers accumulate entries that are vague ("schedule risk"), repeat each other under different titles, lack condition-consequence structure, name no trigger, name no owner, or carry mitigations that are unaccountable. The register becomes a list of words rather than a usable tool for program decisions.

## 3. Intended outcome

A cleaned register with consistent condition-consequence statements, explicit triggers, named owners, current probability and impact, current response status, and a separate list of duplicates merged or candidates retired. The risk owners (not AI, not Tom alone) sign off on the cleaned entries before they replace the original.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Synthetic for personal practice. Real risk register content is Employer-approved at best.
- **Tool environment** (same file, "Tool environments"): Personal AI tool (Gemini-first) for Synthetic input. Employer-approved AI tool only with explicit approval for risk content.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard for synthetic practice. Strict for any real register.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Risk and issue triage outputs.

## 5. Safe inputs

- Synthetic risk register entries with fictional risks, owners, and mitigations.
- Generic risk examples from public PMI material.
- Tom's own notes from public risk-management training.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Real risk registers from any employer system without explicit approval.
- Real owner names, contract risks, customer risks, or financial exposure detail.
- Risks that reveal restricted technical or program content.

## 7. Output format

A two-part Markdown output:

**Part 1 - Cleaned register table**

| # | Condition | Consequence | Trigger | Owner | Probability | Impact | Response (avoid / mitigate / transfer / accept) | Response status | Notes |
|---|---|---|---|---|---|---|---|---|---|

**Part 2 - Hygiene notes**

- Duplicates merged (cite original entry numbers).
- Candidates for retirement (entries where the trigger has passed or the condition is no longer present).
- Entries with missing fields (no owner, no trigger, no response).
- Themes (e.g., "three entries are really the same dependency risk under different framings").

## 8. Tool assumption

Gemini-first and platform-agnostic. Default tool environment is a Personal AI tool with a synthetic register. The same workflow runs unchanged in an Employer-approved AI tool against an approved register; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom for synthetic practice. For any real register, the risk owners are the accountable approvers; nothing in the cleaned register replaces the original until the risk owners sign off. Review intensity from §4 applies. Reviewer follows the "Risk and issue triage outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: confirm each entry has an owner, confirm categorization matches the underlying judgment (not an AI inference), confirm the mitigation or next step is actionable.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop.
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Provide the register snapshot.** Paste the current register as a table with whatever columns it has today.
4. **Ask AI to rewrite vague statements.** Prompt the AI to convert each entry into condition-consequence form ("If X happens, then Y occurs because Z"). Flag entries where condition or consequence cannot be inferred without owner input.
5. **Ask AI to flag missing fields.** AI labels each entry's missing fields (no trigger, no owner, no response status, etc.). AI does not fill missing fields by inference.
6. **Ask AI to propose duplicates and retirement candidates.** AI suggests, with reason; Tom and the risk owners decide.
7. **Risk-owner sign-off.** For real registers, no cleaned entry replaces the original until the risk owner has agreed to the condition, consequence, trigger, probability, impact, and response. For synthetic practice, Tom signs off as the standin owner.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: sign-off line in the output. For employer-deployable runs, full audit envelope per §12.

## 11. Quality checks

Good output:
- Every entry has condition, consequence, trigger, owner.
- Probability and impact match the judgment, not an AI guess.
- Responses are actionable and owned.
- Duplicates and retirement candidates are clearly separated, not silently merged.
- Missing fields are labeled "missing," not filled by inference.

Red flags:
- AI invents an owner.
- AI assigns probability and impact without basis.
- Mitigations described in generic terms ("will monitor") without an owner or trigger.
- A merged entry that loses material from one of the originals.
- Sensitive content (program names, customer detail) inside the cleaned register that should not be there.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For an employer-deployable run, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": register snapshot, tool, operator, reviewer (risk owners), accountable owner (program lead), date, outcome (merges, retirements, sign-offs), storage location inside the approved employer venue.

## 13. Failure modes and escalation triggers

Failure modes:
- AI invents owners, triggers, or response statuses.
- AI silently retires a risk that still applies.
- AI merges entries that are actually distinct risks with shared symptoms.
- Probability and impact get inflated or deflated without judgment behind them.
- Reviewer accepts the cleaned register without risk-owner sign-off.

Escalation triggers (stop iterating the AI draft, go to a human):
- A risk crosses into safety, compliance, or contract obligation - go to program lead and accountable owner directly.
- A risk is owned by someone who has not yet seen the cleaned entry - go to that owner before any official update.
- A risk turns out to involve Prohibited data (real customer behavior, real contract terms) - stop, do not use AI; reclassify.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Synthetic register, Personal AI tool, Standard review, sign-off line.
- **Employer-deployable form (after approval):** Real register, Employer-approved AI tool against approved scope, Strict review, risk-owner sign-off per entry, full audit envelope, stored in approved venue.
- **Re-approval triggers:** Broadening scope to risk-response modeling or quantitative analysis; including contract or customer-facing risks; new tool environment. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0011.
- Paired Phase 5 prompt: A-0042 Risk Register Cleanup Prompt (TBD in Phase 5).
- Related demo: A-0052 Synthetic Risk Register Cleanup Demo (Phase 7).
- Related workflows: W-08 (issue and discrepancy triage).
