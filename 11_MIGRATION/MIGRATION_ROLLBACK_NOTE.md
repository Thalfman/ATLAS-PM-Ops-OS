# MIGRATION_ROLLBACK_NOTE.md

## Artifact identity

- **Backlog ID:** A-0061
- **Phase:** 11 - Employer Migration Plan
- **Parent file:** `11_MIGRATION/EMPLOYER_MIGRATION_PLAN.md`
- **Sibling file:** `11_MIGRATION/PER_ARTIFACT_MIGRATION_READINESS_CHECKLIST.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A short fillable template Tom completes for each migrated artifact, capturing the rollback plan that the per-artifact migration readiness checklist Gate 6 names. A migration without a tested rollback is not a migration. The rollback note exists so a future operator (Tom or the accountable employer owner) can reverse the migration cleanly if a trigger condition occurs.

## Governance envelope

- **Data category:** Tom-personal for the rollback template; the filled-in rollback note for a real artifact is Employer-approved and lives in the employer audit venue.
- **Tool environment:** ATLAS-local Markdown for the template; the filled rollback note lives where the migrated artifact lives.
- **Review intensity:** Standard for the template; Strict for any real rollback execution.
- **Per-domain review pattern:** Status and reporting outputs (when discussed with the manager / reviewer).

## Use rules

- One rollback note per migrated artifact. Bulk rollbacks share fate with bulk migrations: not allowed.
- The rollback owner is named explicitly. The owner is not "Tom" alone unless Tom is explicitly the accountable employer owner.
- Reversibility is tested at the pilot stage. "We described a rollback" is not the same as "we tested it."
- Trigger conditions are explicit. "We'll roll back if it doesn't work" is not a trigger; "we'll roll back if the audit reviewer rejects the next two outputs" is a trigger.
- The rollback note is reviewed at the migrated artifact's next steady-state review (quarterly, annually, or on trigger). Stale rollback notes are no rollback at all.

## Rollback note template

```text
Migration rollback note
Artifact ID / Title: [Migrated artifact's location in the employer venue, and the ATLAS source it migrated from]
Migration date: [YYYY-MM-DD]
Rollback owner: [Role and name]
Reviewer (accepts the rollback plan): [Role and name]
Last reviewed: [YYYY-MM-DD]
Next review: [YYYY-MM-DD or "on trigger"]

1. What rollback means for this artifact
[One paragraph: what state the artifact returns to (e.g., "retired in the employer venue; personal-preparation reference copy in ATLAS remains unchanged"), what users are notified, what audit record is updated.]

2. Trigger conditions
- [Trigger 1: explicit, measurable. e.g., "Audit reviewer rejects two consecutive outputs in the artifact's review cadence."]
- [Trigger 2]
- [Trigger 3]

3. Trigger detection
[Who detects the trigger and how. e.g., "Reviewer flags during the standing review; trigger is recorded in the audit venue within one business day."]

4. Rollback steps
1. [Step 1: explicit, testable. e.g., "Mark the artifact `Retired` in the employer venue and add the retirement reason."]
2. [Step 2: e.g., "Notify the documented user list (defined at migration time)."]
3. [Step 3: e.g., "Update the audit record with the rollback decision, the date, and the named reviewer."]
4. [Step 4: e.g., "Confirm the personal-preparation reference copy in ATLAS is unchanged; mark the migration plan with the rollback outcome."]
5. [Step N]

5. Data disposition
[What happens to outputs produced under the migrated artifact. e.g., "Retained per the employer's standing retention policy for outputs of that category; not deleted; not exported to a personal tool."]

6. Reversibility test record
[When was the rollback last tested (at pilot, at last review)? What happened? Any findings?]

7. Out-of-scope for this rollback note
[What is explicitly not handled here. e.g., "Re-migration after rollback follows the per-artifact migration readiness checklist as a new migration, not an unchecked re-launch."]

8. Approval
- Drafted by [Tom] on [YYYY-MM-DD].
- Reviewed by [accountable employer reviewer] on [YYYY-MM-DD].
- Adjustments after review: [list or "none"].
```

## Failure modes

- Rollback owner left as "Tom" alone when Tom is not the accountable employer owner. Reassign to the actual accountable role.
- Trigger conditions are vague ("if things go wrong"). Replace with specific, measurable conditions.
- Reversibility never tested. A migration whose rollback was never tested has no rollback.
- Rollback steps include "figure out what to do next" rather than concrete actions. Specify or stop.
- The note is filled in once and never reviewed. Add to the artifact's standing review cadence; flag in the knowledge base index if stale.
- Re-migration after rollback skips the readiness checklist. The checklist is required for every migration, including re-launches.

## Cross-references

- Parent file: `11_MIGRATION/EMPLOYER_MIGRATION_PLAN.md`.
- Sibling file: `11_MIGRATION/PER_ARTIFACT_MIGRATION_READINESS_CHECKLIST.md` (Gate 6 cross-references this note).
- Governance bundle: `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`, `06_GOVERNANCE/PROMPT_AND_OUTPUT_RETENTION_NOTE.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0061.
- Decision log: D-0058..D-0060 (Phase 11 set).
