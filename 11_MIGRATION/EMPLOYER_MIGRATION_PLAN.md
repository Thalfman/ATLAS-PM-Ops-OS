# EMPLOYER_MIGRATION_PLAN.md

## Artifact identity

- **Backlog ID:** A-0025
- **Phase:** 11 - Employer Migration Plan
- **Sibling files:** `11_MIGRATION/PER_ARTIFACT_MIGRATION_READINESS_CHECKLIST.md`, `11_MIGRATION/MIGRATION_ROLLBACK_NOTE.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A personal-preparation plan describing how Tom intends to migrate approved ATLAS workflows, prompts, and templates from personal use to employer-approved tools — once explicit approvals exist for the specific tool, the specific data category, and the specific artifact. The plan names the discipline. The plan does **not** authorize migration; only the employer authorizes that.

This is personal preparation material. Any conflict with explicit employer instruction is resolved in favor of the employer instruction.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`): Tom-personal. The plan describes Tom's intended discipline; it carries no employer data.
- **Tool environment:** ATLAS-local Markdown only. The migration described inside the plan happens entirely in employer-approved tools; the plan itself is not the migration.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`): Standard for the plan itself; Strict for any actual migration activity that touches employer data.
- **Per-domain review pattern:** Status and reporting outputs (when discussing the plan with the manager).

## Core posture (binding)

1. **Migration is gated by employer approval.** Nothing in this plan pre-authorizes any specific tool, any specific data category, or any specific artifact. The plan describes the discipline Tom will follow once approvals exist.
2. **Personal-preparation artifacts stay personal until explicit approval.** Per D-0026, a personal-preparation artifact does not become an employer-deployable artifact by being copy-pasted into an employer tool. Conversion requires written or otherwise documented approval.
3. **The six-step pattern is non-negotiable.** Every migration walks the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`: identify candidate, classify data path, identify approved tool environment, define human review point, pilot safely, document / request approval / record decision.
4. **No shadow migration.** No personal-account workarounds, no exporting employer data to a personal tool for "easier formatting," no paraphrasing restricted content into a personal note to feed back into an approved tool later.
5. **Reversibility is a requirement.** Every migrated artifact has a documented rollback (see `MIGRATION_ROLLBACK_NOTE.md`). A migration that cannot be rolled back is not a migration; it is a one-way data leak.
6. **Audit trail lives in the approved venue.** Migration audit records (who approved, when, what tool, what data scope) live in the employer's audit system, not in ATLAS.
7. **The plan is conservative on purpose.** If a Codex review, manager conversation, or stakeholder request would loosen any rule above, surface as a posture issue and log a new decision rather than silently relaxing the rule.

## Migration scope categories

Each ATLAS artifact falls into one of these categories. The migration approach differs by category.

### A. Personal preparation only — no migration intended

These artifacts stay in ATLAS and are not candidates for migration. They support Tom's personal practice.

- The 14 phase prompt files under `05_PROMPTS/PHASE_PROMPTS/`.
- `00_MASTER_CONTEXT/MASTER_CONTEXT.md`, `09_HANDOFFS/SESSION_HANDOFF.md`, `10_DECISION_LOG/DECISION_LOG.md`.
- The Phase 6 First-Week Readiness Kit (`07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md` and sub-files) — personal-preparation, by design.
- The Phase 7 synthetic demo pack and shared scenario.
- The Phase 8 synthetic schedule workbook and Phase 9 synthetic EVM workbook / accounting demo.

### B. Conditionally migratable — after explicit approval

These artifacts have an employer-deployable form once approval exists. Migration produces a new artifact in the approved venue; the personal version stays in ATLAS for reference.

- The 15 workflow cards under `04_WORKFLOWS/` (W-01..W-15, W-17). Each card's §14 already names the migration triggers.
- The 11 paired prompt cards under `05_PROMPTS/` (P-01..P-12 skipping reserved gaps) plus P-00 and P-99 utilities.
- The Phase 8 templates (`SCHEDULE_HEALTH_REVIEW_TEMPLATE.md`, `SCHEDULE_VARIANCE_NARRATIVE_TEMPLATE.md`).
- The Phase 10 templates (`SOP_TEMPLATE.md`, `LESSONS_LEARNED_TEMPLATE.md`, `KNOWLEDGE_BASE_PATTERN.md`).
- The Phase 9 W-17 workflow card.

### C. Governance and rules — never migrated, only referenced

These artifacts describe Tom's personal-preparation discipline. They are not deployed inside employer systems. Employer governance documents are the authoritative source inside the company; ATLAS governance is Tom's personal preparation.

- All files under `06_GOVERNANCE/`.
- This migration plan and its siblings.

## Phased migration approach

Migration runs in three phases per artifact. Skipping a phase requires a new logged decision.

### Phase M1 — Approval

1. Walk the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.
2. Confirm tool is on the approved list for the data category. If the tool is not approved, stop and route to IT.
3. Confirm data category routing per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If routing is unclear, stop and route to security.
4. Confirm a named human reviewer accepts the role for the migrated artifact.
5. Document the approval (in the employer venue) before any artifact moves.

### Phase M2 — Pilot

1. Move one artifact at a time, not in bulk.
2. Run the artifact against synthetic or sanitized inputs first — never against real employer data on the first pilot.
3. Walk the pre-flight and post-flight checklists from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`.
4. Capture pilot findings in the employer venue's audit record.
5. Decide go / no-go before any real-data use. A no-go is a complete answer.

### Phase M3 — Steady-state

1. The migrated artifact's owner role takes over.
2. Personal-preparation version stays in ATLAS as the reference; it does not receive employer-data updates.
3. Changes to the employer version flow back to ATLAS as patterns or lessons (not as data).
4. Review cadence per the per-artifact migration readiness checklist; rollback note kept current.

## When the plan applies vs when it does not

**Applies when:**
- Tom has explicit employer approval to migrate a specific artifact to a specific tool.
- An accountable employer reviewer has accepted the role.
- The data category routing is documented and consistent with `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`.

**Does not apply when:**
- No explicit approval exists, regardless of how "obviously useful" a migration would be.
- A request to "just try it informally" arrives. Informal use is shadow migration.
- The data path is ambiguous. Ambiguous means stop, not "default to allowed."

## Things this plan deliberately does not do

- Does not name specific employer tools (Gemini Enterprise, SharePoint, Microsoft Project, etc.) as approved or unapproved. Approval status is the employer's call.
- Does not commit Tom to a migration schedule. Sequence is decided per artifact once approvals exist.
- Does not authorize Tom to act as a migration owner without explicit assignment.
- Does not describe what is allowed inside the employer environment. Employer policy is authoritative inside the company.
- Does not promise that ATLAS artifacts will be useful inside any specific employer environment. Usefulness is an empirical question that the pilot phase answers.

## How this plan is used in conversation

- With the manager: "I have a personal-preparation plan describing the discipline I'd follow if approvals were in place. I'm not asking to deploy anything; I'm clarifying the posture."
- With IT or security: "Here is my data-classification model (`DATA_SENSITIVITY_DECISION_MODEL.md`) and my six-step approval pattern (`AI_TOOL_APPROVAL_STRATEGY.md`). I'd like to understand the approved tool list and the request process before proposing anything."
- With program leadership: "ATLAS is personal preparation. Migration to anything that touches real program content would require explicit approval first; I'm conservative on that."

The `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md` provides talking-point detail.

## Revision triggers

Update this plan when:

- Employer policy becomes known and changes a posture assumption.
- A new ATLAS artifact category is added (e.g., a new W-NN or a new template directory).
- An actual migration occurs and the pilot surfaces a discipline gap.
- The Phase 12 final review (`PHASE_12_FINAL_OPERATING_SYSTEM_REVIEW.md`) recommends a change.

Log each revision in `10_DECISION_LOG/DECISION_LOG.md` with the trigger and the rule that changed.

## Cross-references

- Sibling files: `11_MIGRATION/PER_ARTIFACT_MIGRATION_READINESS_CHECKLIST.md` (fill in per artifact); `11_MIGRATION/MIGRATION_ROLLBACK_NOTE.md` (rollback template).
- Governance bundle: `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`, `06_GOVERNANCE/EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md`, `06_GOVERNANCE/PROMPT_AND_OUTPUT_RETENTION_NOTE.md`.
- Phase 6 conversation support: `07_TEMPLATES/AI_INTEGRATION_DISCUSSION_GUIDE.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0025.
- Decision log: D-0058..D-0060 (Phase 11 set).
