# PROMPT_LIBRARY.md

## Library purpose

The ATLAS prompt library is the set of Gemini-first, copy-paste-ready prompts Tom uses to drive the AI-drafting steps inside ATLAS workflows. Each prompt pairs against exactly one workflow card in `04_WORKFLOWS/`. Prompts inherit the Phase 3 governance envelope and the paired workflow card's inputs, output format, review pattern, and migration notes; they do not redefine policy.

This file is the index. The reusable schema lives in `05_PROMPTS/PROMPT_CARD_TEMPLATE.md`. Each prompt lives in its own `05_PROMPTS/P-NN-<slug>.md` file. Two utility prompts (`P-00` safety precheck and `P-99` critique / output QA) sit outside the 11/15 pairing because they apply to every prompt.

## Universal prompt rules

1. Run `P-00-safety-precheck.md` before sending any prompt. If the precheck fails, the AI step does not run.
2. Use placeholders, never real employer data. Personal-preparation prompts use fictional or Tom-personal content only.
3. Forbid invention. Every prompt instructs the AI to flag missing fields rather than guess them.
4. Forbid AI decisions. Every prompt restricts the AI to structuring, summarizing, drafting, or flagging inconsistencies. The AI never approves, escalates, sends, or commits.
5. Keep a named human reviewer. Output is a draft until a named human signs off per the review intensity in the paired workflow card's §4.
6. Cite, do not redefine. Each prompt cites the Phase 3 governance files and the paired W-NN card by filename. Output format mirrors the paired W-NN §7.

## Governance bundle (single source of truth - do not redefine)

Every prompt card cites these by filename and section:

- `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md` - five data categories (Synthetic, Public, Tom-personal, Employer-approved, Prohibited) and four tool environments. When in doubt: more restrictive (D-0024).
- `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` - three review intensities (Light, Standard, Strict), six per-domain review patterns, pre-flight and post-flight checklists, auditability minimums (D-0023).
- `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` - six-step approval pattern before any AI use case touches employer data. Cited in every card's §11 "Notes for approved-tool migration" (D-0025).
- `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md` - personal-preparation vs employer-deployable distinction. Implicit in every card's §11 (D-0026).

## Standard prompt card schema

Each prompt card follows the 14-section schema in `05_PROMPTS/PROMPT_CARD_TEMPLATE.md`. Section order is fixed: identity, then use case (§§1-2), then governance envelope (§3), then inputs and prohibitions (§§4-5), then placeholders (§6), then the copy-paste prompt text (§7), then output shape (§8), then human review (§9), then failure modes (§10), then migration (§11), then safety precheck and output critique (§§12-13), then cross-references (§14).

To add a new prompt:

1. Copy `PROMPT_CARD_TEMPLATE.md` to the next free `P-NN-<slug>.md` (numbering parallels the paired W-NN where one exists; otherwise the next available number after the existing P-NN set).
2. Populate all 14 sections. Do not leave placeholders unfilled.
3. Append a row to the index table below.
4. If pairing with a W-NN card, update that card's §15 "Paired Phase 5 prompt" line.
5. Update the matching `03_BACKLOG/ARTIFACT_BACKLOG.md` row so Notes points at the P-NN file and Status reflects readiness.
6. If the new prompt introduces a durable design choice (new pattern, new constraint, new utility prompt), log it in `10_DECISION_LOG/DECISION_LOG.md` in the same session.

## Prompt index

| P-ID | Prompt | Paired W-ID | Backlog A-ID | Data category | Review intensity | File |
|---|---|---|---|---|---|---|
| P-00 | Universal safety precheck | (utility) | (none) | n/a | n/a | `P-00-safety-precheck.md` |
| P-01 | Weekly status drafting | W-01 | A-0039 | Synthetic / Tom-personal | Standard | `P-01-weekly-status-drafting.md` |
| P-02 | Meeting notes to actions | W-02 | A-0040 | Tom-personal | Standard | `P-02-meeting-notes-to-actions.md` |
| P-03 | Action aging summary | W-03 | A-0041 | Tom-personal | Standard | `P-03-action-aging-summary.md` |
| P-04 | (no dedicated prompt) | W-04 schedule health | (none) | — | — | — |
| P-05 | Schedule variance narrative | W-05 | A-0047 | Synthetic | Standard | `P-05-schedule-variance-narrative.md` |
| P-06 | EVM variance explanation | W-06 | A-0018 | Synthetic | Standard | `P-06-evm-variance-explanation.md` |
| P-07 | Risk register cleanup | W-07 | A-0042 | Synthetic | Standard | `P-07-risk-register-cleanup.md` |
| P-08 | Issue and discrepancy triage | W-08 | A-0043 | Synthetic | Standard | `P-08-issue-and-discrepancy-triage.md` |
| P-09 | Accounting reconciliation narrative | W-09 | A-0019 | Synthetic | Standard | `P-09-accounting-reconciliation-narrative.md` |
| P-10 | Lessons learned capture | W-10 | A-0046 | Synthetic | Standard | `P-10-lessons-learned-capture.md` |
| P-11 | SOP first draft | W-11 | A-0045 | Synthetic | Standard | `P-11-sop-first-draft.md` |
| P-12 | Executive brief drafting | W-12 | A-0044 | Synthetic / Tom-personal | Standard | `P-12-executive-brief-drafting.md` |
| P-13 | (no dedicated prompt) | W-13 cross-tool mismatch | (none) | — | — | — |
| P-14 | (no dedicated prompt) | W-14 Google Workspace knowledge | (none) | — | — | — |
| P-15 | (no dedicated prompt) | W-15 clearance-limited onboarding | (none) | — | — | — |
| P-99 | Prompt critique / output QA | (utility) | (none) | n/a | n/a | `P-99-prompt-critique-and-output-qa.md` |

P-04, P-13, P-14, P-15 are intentionally reserved and not authored. Per D-0034, the paired workflows W-04 (structural), W-13 (investigative), W-14 (information-management), and W-15 (personal-planning) carry "Paired Phase 5 prompt: none" in their §15 by design. The 11/15 pairing is deliberate; future sessions must not invent prompts to force a 15/15 mapping.

Review intensity in the table is the default for personal-preparation use. When the same prompt is used against Employer-approved data in an Employer-approved AI tool, review intensity moves to Strict and the §11 migration notes in the card apply.

## Maintenance and decision log

- Prompt card IDs (P-NN) are append-only. Retire a prompt by setting Status to `Deferred`; never reuse an ID. Parallels D-0017 (A-IDs) and D-0030 (W-IDs).
- Schema changes apply to all cards. Update `PROMPT_CARD_TEMPLATE.md` first, then back-port every existing P-NN file in the same session, then log the change.
- The 11/15 pairing is fixed by D-0034. Any future change to the pairing requires a new logged decision.
- `P-00` and `P-99` are utility prompts cited by every paired prompt's §12 and §13. Edits to `P-00` apply universally; review the effect on every paired prompt in the same session.

## Cross-references

- Phase 5 prompt: `05_PROMPTS/PHASE_PROMPTS/PHASE_05_PROMPT_LIBRARY.md`.
- Workflow library index: `04_WORKFLOWS/WORKFLOW_LIBRARY.md`.
- Backlog: `03_BACKLOG/ARTIFACT_BACKLOG.md` (Prompt library section, rows A-0018, A-0019, A-0039..A-0047).
- Decision log: D-0023..D-0027 (Phase 3 governance envelope); D-0029..D-0034 (Phase 4 workflow schema and pairing scope); D-0035..D-0039 (Phase 5 prompt schema, naming, structure, utility prompts, and branch).
