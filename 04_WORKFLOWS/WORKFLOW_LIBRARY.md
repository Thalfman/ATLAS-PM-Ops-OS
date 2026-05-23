# WORKFLOW_LIBRARY.md

## Library purpose

The ATLAS workflow library is the set of manual-first PM/Ops workflow cards Tom uses for personal preparation, synthetic demos, and eventually employer-approved migration. Each card improves project integrity, reporting quality, schedule/accounting reconciliation, discrepancy resolution, action tracking, lessons learned, SOP quality, executive communication, or knowledge capture.

This file is the index. The reusable schema lives in `04_WORKFLOWS/WORKFLOW_CARD_TEMPLATE.md`. Each individual workflow lives in its own `04_WORKFLOWS/W-NN-<slug>.md` file. The Phase 3 governance bundle defines the data envelope and human-review pattern; workflow cards cite that bundle rather than redefining it.

## Universal workflow rules

1. Use only approved tools for employer data.
2. Use only synthetic, public, or Tom-personal data in personal preparation.
3. Keep a human accountable for review and decisions. AI never makes official commitments.
4. Ask AI to structure, compare, summarize, draft, or flag inconsistencies. Do not ask AI to decide, approve, escalate, or send.
5. Preserve audit trails per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: source, tool, operator, reviewer, accountable owner, date, outcome, storage location.
6. Avoid black-box automation until the manual process is accepted and stable.

## Governance bundle (single source of truth - do not redefine)

Every workflow card cites these by filename and section:

- `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md` - five data categories (Synthetic, Public, Tom-personal, Employer-approved, Prohibited) and four tool environments (ATLAS-local Markdown, Personal AI tool, Employer-approved AI tool, No AI tool). When in doubt: more restrictive (D-0024).
- `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` - three review intensities (Light, Standard, Strict) and six per-domain review patterns (Status/Schedule/Finance-EVM/Meeting-notes/Risk-and-issue/SOP-and-lessons-learned). Carries the pre-flight and post-flight checklists. (D-0023)
- `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md` - six-step approval pattern required before any AI use case touches employer data. Cited in every card's "Migration notes" section. (D-0025)
- `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md` - personal-preparation vs employer-deployable distinction. Implicit in every card's "Migration notes" section. (D-0026)

## Standard workflow card schema

Each workflow card follows the 16-section schema in `04_WORKFLOWS/WORKFLOW_CARD_TEMPLATE.md`. The 16 sections cover the 12 required fields from the Phase 4 prompt plus the 4 governance citations plus identity and cross-references. Section order is fixed: identity, then problem (§§1-3), then governance envelope (§4), then inputs and outputs (§§5-8), then human review (§9), then process (§10), then controls (§§11-12), then failure handling (§13), then migration (§14), then cross-references (§15).

To add a new workflow:

1. Copy `WORKFLOW_CARD_TEMPLATE.md` to the next free `W-NN-<slug>.md`.
2. Populate all 16 sections. Do not leave placeholders.
3. Append a row to the index table below.
4. Add or update the matching `03_BACKLOG/ARTIFACT_BACKLOG.md` row so Notes points at the W-NN file and Status reflects readiness.
5. If the new workflow introduces a durable design choice (new pattern, new constraint, new category), log it in `10_DECISION_LOG/DECISION_LOG.md` in the same session.

## Workflow index

| W-ID | Workflow | Backlog ID | Data category | Tool environment | Review intensity | File |
|---|---|---|---|---|---|---|
| W-01 | AI-assisted weekly status report | A-0008 | Synthetic / Tom-personal | Personal AI tool (Gemini-first) | Standard | `W-01-weekly-status-report.md` |
| W-02 | Meeting notes to action items | A-0009 | Tom-personal | Personal AI tool (Gemini-first) | Standard | `W-02-meeting-notes-to-actions.md` |
| W-03 | Action item aging and follow-up | A-0010 | Tom-personal | Personal AI tool (Gemini-first) | Standard | `W-03-action-item-aging.md` |
| W-04 | Microsoft Project schedule health review | A-0015 (Phase 8) | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-04-schedule-health-review.md` |
| W-05 | Schedule variance narrative drafting | A-0016 (Phase 8) | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-05-schedule-variance-narrative.md` |
| W-06 | EVM variance explanation support | A-0066 | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-06-evm-variance-explanation.md` |
| W-07 | Risk register cleanup | A-0011 | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-07-risk-register-cleanup.md` |
| W-08 | Issue and discrepancy triage | A-0012 | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-08-issue-and-discrepancy-triage.md` |
| W-09 | Project accounting reconciliation narrative | A-0036 | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-09-accounting-reconciliation-narrative.md` |
| W-10 | Lessons learned capture | A-0013 (Phase 10) | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-10-lessons-learned-capture.md` |
| W-11 | SOP draft generation | A-0014 (Phase 10) | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-11-sop-draft-generation.md` |
| W-12 | Executive brief generation | A-0067 | Synthetic / Tom-personal | Personal AI tool (Gemini-first) | Standard | `W-12-executive-brief-generation.md` |
| W-13 | Cross-tool data mismatch investigation | A-0037 | Synthetic | Personal AI tool (Gemini-first) | Standard | `W-13-cross-tool-mismatch-investigation.md` |
| W-14 | Google Workspace knowledge workflow | A-0020 | Public / Synthetic | Employer-approved AI tool (Workspace) | Standard | `W-14-google-workspace-knowledge.md` |
| W-15 | Clearance-limited onboarding workflow | A-0068 | Tom-personal | ATLAS-local Markdown / Personal AI tool | Light | `W-15-clearance-limited-onboarding.md` |

Review intensity in the table is the default for personal-preparation use. When the same workflow is run against Employer-approved data in an Employer-approved AI tool, review intensity moves to Strict and the §14 migration notes in each card apply.

## Maintenance and decision log

- Workflow card IDs (W-NN) are append-only. Retire a workflow by setting Status to `Deferred`; never reuse an ID. Parallels the append-only A-ID rule (D-0017).
- Schema changes apply to all cards. Update `WORKFLOW_CARD_TEMPLATE.md` first, then back-port every existing W-NN file in the same session, then log the change.
- Phase 5 prompts pair against these workflows. Each Phase 5 prompt names the W-NN it serves.

## Cross-references

- Phase 4 prompt: `05_PROMPTS/PHASE_PROMPTS/PHASE_04_WORKFLOW_LIBRARY.md`.
- Backlog: `03_BACKLOG/ARTIFACT_BACKLOG.md` (Workflow library section, rows A-0008..A-0012, A-0020, A-0036..A-0038, A-0066..A-0068; cross-referenced rows A-0013..A-0016).
- Decision log: D-0023..D-0027 (Phase 3 governance envelope); D-0029..D-0033 (Phase 4 schema, naming, structure, backlog reconciliation, branch).
