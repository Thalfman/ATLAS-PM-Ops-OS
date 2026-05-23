# KNOWLEDGE_BASE_PATTERN.md

## Artifact identity

- **Backlog ID:** A-0059
- **Phase:** 10 - SOP and Lessons Learned Track
- **Sibling templates:** `07_TEMPLATES/SOP_TEMPLATE.md`, `07_TEMPLATES/LESSONS_LEARNED_TEMPLATE.md`
- **Related workflows:** `04_WORKFLOWS/W-10-lessons-learned-capture.md`, `04_WORKFLOWS/W-11-sop-draft-generation.md`, `04_WORKFLOWS/W-14-google-workspace-knowledge.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

A generic pattern for organizing SOPs and lessons learned so that they are findable, reusable, and traceable. The pattern is tool-agnostic: it works in Google Workspace (`W-14`), Microsoft SharePoint, a Confluence wiki, a Git repo, or any document repository. It exists so that Phase 10 outputs (SOPs and lessons learned) do not become orphan documents that nobody can find or update.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`): Public / Synthetic for the pattern itself; the documents organized by the pattern carry whatever data category their content carries.
- **Tool environment:** ATLAS-local Markdown for the pattern; deployed knowledge bases live in an Employer-approved venue after approval.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`): Standard for personal practice; Strict for any deployed knowledge base.
- **Per-domain review pattern:** SOP and lessons-learned outputs.

## Use posture

- Findability is the goal. A new operator should be able to locate a relevant SOP or lessons-learned entry within two minutes.
- Reusability is the goal. SOPs and lessons should be linked, not copy-pasted; an update to one source propagates by reference.
- Traceability is the goal. Every entry names its owner role, its last review, and its next review.
- The pattern is conservative: a working knowledge base is better than an aspirational one. Start small; grow under load.

## Pattern (six elements)

### 1. Naming and addressing

- Each entry has a stable ID (SOP-NNN, LL-NNN) that does not change when the entry's content changes.
- Entry titles are verb-led and scope-bounded ("Reconcile weekly status pack to action tracker," not "Reporting stuff").
- The folder or path structure mirrors the operating model (e.g., one folder per workstream or one per process area), not the org chart.
- Avoid duplicate titles. If two entries have the same title, one should reference the other or they should be merged.

### 2. Metadata

Every entry carries:

- Owner role (not a person).
- Approver role.
- Last reviewed date.
- Next review date (or "on trigger" with the trigger named).
- Status: Draft / Approved / Retired.
- Cross-references to related SOPs, lessons, workflows, and prompt cards.
- Source-of-truth note: where the canonical version lives.

### 3. Findability

- A flat index that lists every SOP and lessons-learned entry with ID, title, owner role, status, and last reviewed date.
- Search tags (4-6 per entry) keyed to the operating-model vocabulary, not free-text.
- A "where to start" landing page that names the top 5-10 entries new operators most often need.
- A "what's new" feed listing recently approved or retired entries (last 30-60 days).

### 4. Reuse over copy

- SOPs reference templates rather than embedding them.
- Lessons reference the SOP or workflow they update; the SOP is updated from the lesson, not vice versa.
- Common process fragments (e.g., a standard sign-off block) live as snippets that other entries include by reference.
- If a copy must exist (e.g., for an approval venue that cannot link), the copy names its source and revision so a future reader can verify currency.

### 5. Review cadence

- Every entry has a named review cadence (quarterly, annually, on trigger).
- Reviews are tracked in an index, not just in the entry's revision history.
- "On trigger" cadences name the trigger explicitly (e.g., "review when the paired workflow card is updated").
- Entries past their review date are flagged in the index; flagged entries either get reviewed or retired.

### 6. Retirement

- Retiring an entry is a first-class action, not a deletion. Retired entries stay in the index with status `Retired` and a retirement reason.
- Retirement reasons name what replaced the entry (an ID or title) or why it is no longer needed.
- A retired entry's cross-references are checked: every entry that linked to it gets an update or a note.

## Implementation in tool-specific environments

The pattern is tool-agnostic, but the implementation differs:

- **Google Workspace** (W-14 governance applies): folder structure plus a master index Sheet plus search tags in Doc metadata. Source of truth is the Doc; the Sheet is the index.
- **Microsoft SharePoint:** site structure plus a master list view; tag with managed metadata; check-in / check-out controls support review cadence.
- **Confluence / wiki:** spaces and pages with labels; macros (e.g., "page properties report") generate the index automatically.
- **Git repo (this repo is an example):** folders per phase or area; `WORKFLOW_LIBRARY.md` / `PROMPT_LIBRARY.md`-style index files; cross-references by file path.

The pattern does not require any specific tool. It requires that the chosen tool can support stable IDs, metadata, an index, links, review tracking, and retirement.

## Failure modes

- Knowledge base grows by addition without retirement; the "graveyard" of stale entries dominates and findability collapses.
- Entries are copy-pasted instead of linked; an update to one copy does not propagate.
- Owner role is named as a person; when the person leaves, the entry becomes orphaned.
- Search tags are free-text rather than keyed to the operating-model vocabulary; search degrades to keyword matching.
- "Next review date" is set but never enforced; entries drift past review without action.
- Retirement is treated as deletion; cross-references break silently.

## Migration notes (post-clearance, post-approval)

- **Personal-preparation form (today):** This file is the pattern; ATLAS itself is a partial instantiation of the pattern (see `04_WORKFLOWS/WORKFLOW_LIBRARY.md`, `05_PROMPTS/PROMPT_LIBRARY.md`, `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md` as index examples).
- **Employer-deployable form:** Pattern applies unchanged. Tool environment shifts to whichever knowledge-base venue the employer approves. Document content's data category follows its source (Synthetic / Public / Employer-approved). Reviewer named per employer policy.
- **Re-approval triggers:** Any deployed knowledge base needs initial approval. Adding a new content category to the knowledge base requires re-walking the six-step pattern in `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`.

## Cross-references

- Sibling templates: `07_TEMPLATES/SOP_TEMPLATE.md`, `07_TEMPLATES/LESSONS_LEARNED_TEMPLATE.md`.
- Related workflows: `04_WORKFLOWS/W-10-lessons-learned-capture.md`, `04_WORKFLOWS/W-11-sop-draft-generation.md`, `04_WORKFLOWS/W-14-google-workspace-knowledge.md`.
- Examples of the pattern instantiated in ATLAS: `04_WORKFLOWS/WORKFLOW_LIBRARY.md`, `05_PROMPTS/PROMPT_LIBRARY.md`, `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`, `08_SYNTHETIC_DEMOS/SYNTHETIC_DEMO_PACK.md`.
- Governance bundle: `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `AI_GOVERNANCE_NOTES.md`.
- Backlog row: `03_BACKLOG/ARTIFACT_BACKLOG.md` A-0059.
- Decision log: D-0055..D-0057 (Phase 10 set).
