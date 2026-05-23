# W-14-google-workspace-knowledge - Google Workspace knowledge workflow

## Workflow identity

- **ID:** W-14
- **Backlog ID:** A-0020
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## 1. Workflow name

Google Drive, Docs, and Sheets knowledge workflow.

## 2. PM/Ops problem addressed

Workspace tools (Drive, Docs, Sheets) accumulate content quickly and become unfindable: inconsistent naming, untagged ownership, sprawling folder hierarchies, duplicate docs, and Sheets whose source-of-truth status is unclear. Knowledge gets re-created instead of reused, and external sharing carries risk because ownership is unclear.

## 3. Intended outcome

A repeatable pattern for placing, naming, owning, tagging, and sharing knowledge in an approved Google Workspace so that findability and reuse improve, link ownership is verified before sharing, and source-of-truth Sheets are clearly distinguished from working copies.

## 4. Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Public for public material; Synthetic for ATLAS practice content; Tom-personal for Tom's own notes. Employer-approved when running against employer Workspace content within approved scope.
- **Tool environment** (same file, "Tool environments"): Employer-approved AI tool (Workspace AI features) when the Workspace itself is the employer's approved environment. ATLAS-local Markdown for the pattern description itself.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Standard. Strict for any document shared externally.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): SOP and lessons-learned outputs (this workflow is itself an information-management SOP).

## 5. Safe inputs

- Public material being curated into a Workspace.
- Synthetic ATLAS demo content for personal practice.
- Tom's own non-restricted notes.
- Employer-approved content within approved scope, run inside the Workspace's approved AI features.

## 6. Prohibited inputs

In the default personal-preparation environment (§4), the following inputs are prohibited. Employer-deployable use against employer-approved data requires explicit approval per §14 and the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

- Restricted content uploaded to a personal Drive or unapproved Workspace.
- Content shared externally without verified link ownership.
- Sheets used as source of truth without clear ownership and review cadence.

## 7. Output format

A two-part Markdown output:

**Part 1 - Workspace placement record (per artifact)**

| Field | Value |
|---|---|
| Artifact name | |
| Type (Doc / Sheet / Slide / file / folder) | |
| Location (folder path) | |
| Owner (role) | |
| Tag / label | |
| Source-of-truth flag | yes / no / working copy |
| Sharing scope | internal-only / specific people / domain / external (justification required) |
| Review cadence | |

**Part 2 - Naming and tagging conventions**

- Naming pattern (e.g., `[program] - [artifact type] - [version/date]`).
- Tag taxonomy (working / draft / current / archived).
- Folder hierarchy rule.
- Source-of-truth Sheet marker (e.g., `SOT-` prefix).
- Sharing-scope decision tree (one short flow: internal only? specific people? domain? external?).

## 8. Tool assumption

The pattern is portable across Workspaces. The default deployment is an Employer-approved Workspace once approval exists. The ATLAS pattern description itself lives in Markdown. Same workflow runs unchanged when applied to an approved Workspace; see §14.

## 9. Human-in-the-loop review point

Named human reviewer: Tom for personal Workspace. For any employer Workspace, the accountable owner is whoever owns the content domain (program lead, knowledge owner). For any external sharing, Tom verifies link ownership and sharing scope before sending. Review intensity from §4 applies. Reviewer follows the "SOP and lessons-learned outputs" pattern in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`: confirm the placement record describes the actual artifact, confirm conventions are testable, confirm sharing scope does not violate fairness or policy.

## 10. Step-by-step process

1. **Classify the input.** State data category and tool environment in one line per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`. If uncertain, stop. (Note: any Employer-approved content stays inside the approved Workspace; ATLAS-local Markdown does not store it.)
2. **Pre-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Pre-flight checklist before invoking AI."
3. **Define purpose.** State why this artifact exists and who needs to find it.
4. **Apply naming, location, owner, tag.** Use the conventions in §7. Set source-of-truth flag deliberately - no implicit source-of-truth Sheets.
5. **Verify link ownership before sharing.** Confirm the file is owned by the right account and that link sharing reflects the intended scope.
6. **Verify sharing scope.** Walk the sharing-scope decision tree. External sharing requires explicit justification recorded in the placement record.
7. **Record review cadence.** Every source-of-truth artifact has a review cadence and a named owner.
8. **Post-flight checklist.** Run the checklist in `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Post-flight checklist before using AI output."
9. **Record sign-off.** Standard intensity: placement record itself serves as sign-off. For externally shared or employer-deployable artifacts, full audit envelope per §12.

## 11. Quality checks

Good output:
- Naming is consistent and predictable.
- Source-of-truth artifacts are clearly flagged.
- Sharing scope is verified and justified where it exceeds internal.
- Each artifact has an owner and a review cadence.
- Working copies are distinguishable from current source-of-truth.

Red flags:
- An artifact with no owner.
- A source-of-truth Sheet that is not flagged.
- External sharing without recorded justification.
- Naming that varies between sibling artifacts in the same folder.
- A Doc whose Title and content disagree on what it covers.

## 12. Audit and logging notes

For personal preparation, the audit trail is this repo's commit history plus the matching session in `09_HANDOFFS/SESSION_HANDOFF.md`. For employer Workspace use, the audit trail is the Workspace's own activity history plus the placement record; for externally shared artifacts, capture the full audit envelope from `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` "Auditability minimums": source content, tool (Workspace + any AI features used), operator, reviewer, accountable owner, date, outcome, sharing scope and justification.

## 13. Failure modes and escalation triggers

Failure modes:
- AI suggests a naming or tagging convention that conflicts with the employer's existing convention.
- Source-of-truth flag set on a working copy.
- Link sharing scope set wider than intended by default.
- Tag taxonomy drifts across folders.
- Review cadence ignored after the placement record is created.

Escalation triggers (stop iterating the AI draft, go to a human):
- External sharing involves customer-facing content - go to manager and compliance.
- Naming or location convention conflicts with an existing employer convention - adopt the employer convention, log the change.
- Workspace AI features turn out to operate outside approved scope - stop using those features for the content, escalate to IT or security.

## 14. Migration notes for approved employer systems

- **Personal-preparation form (today):** Patterns described in this card and applied to Tom's personal Workspace or to ATLAS practice content.
- **Employer-deployable form (after approval):** Patterns adapted to the employer's Workspace conventions where they exist; Workspace AI features used only inside approved scope; placement records kept in the approved venue; full audit envelope for shared artifacts.
- **Re-approval triggers:** Using Workspace AI features against new data categories; sharing artifacts externally; broadening scope to automated tagging or summarization. Each requires re-walking the six-step approval pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## 15. Cross-references

- Phase 3 governance: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0020.
- Paired Phase 5 prompt: none. This workflow is information-management (placement, naming, sharing-scope pattern, not drafting); AI's role is structural, so no dedicated prompt is needed in the Phase 5 prompt library (A-0018, A-0019, A-0039..A-0047).
- Related artifact: A-0059 Knowledge Base Pattern (Phase 10).
- Related workflows: W-11 (SOP draft generation) for the SOP describing this pattern.
