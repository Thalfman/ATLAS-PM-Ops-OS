# Phase 05 Prompt - Prompt Library

## Phase

Phase 5: Prompt Library

## Purpose

Create reusable, safe, copy-paste-ready prompts for ATLAS PM/Ops workflows.

## Copy-paste prompt

```text
Continue ATLAS PM/Ops OS.

Local repo path:
C:\Users\thalf\OneDrive\Documents\ATLAS-PM-Ops-OS

Project context:
ATLAS PM/Ops OS means AI-enabled Tactical Learning, Automation, and Systems. It is a durable, local, Markdown-first PM/Ops operating system for Tom Halfman, PMP, as he prepares for and starts a Project Manager / Operations Specialist role in Motorola Solutions Applied Technology in Schaumburg.

Role positioning:
Tom is entering as a PMP-certified PM/Ops/project-controls professional with AI/ML fluency, not as the deepest RF engineer. His expected value includes project integrity, schedule and budget governance, EVM support, project accounting reconciliation, reporting quality, process compliance, discrepancy resolution, lessons learned, SOPs, dashboards, repeatable operating systems, and responsible AI workflow integration.

Important AI context:
Responsible AI integration is a major expected value area for Tom in the role. The goal is not AI hype or tool chasing. The goal is practical, auditable PM/Ops improvement using approved tools and human judgment.

Known environment assumptions:
- Gemini Enterprise may be the only approved AI tool at first.
- Google Workspace is likely common.
- Microsoft Project is used.
- Excel and internal reporting systems are likely used.
- Claude, OpenAI, Codex, APIs, CLI tools, and MCP may not be approved at work initially.
- Design Gemini-first and platform-agnostic so workflows can later migrate to approved tools, APIs, MCP, OpenAI, Claude, Microsoft Copilot, internal LLMs, or other enterprise systems if approved.

Hard safety boundary:
Use only synthetic data, public information, generic examples, fictional project scenarios, and non-proprietary templates. Do not request, include, transform, summarize, or infer from classified data, CUI, ITAR/export-controlled data, proprietary employer data, customer data, contract data, internal schedules, internal financials, internal technical documents, real meeting notes, real project accounting exports, real Microsoft Project files from employer systems, or any employer data not explicitly approved for the system being used.

Default posture:
- Human-in-the-loop.
- Audit-friendly.
- Approved-tool-first.
- No shadow IT.
- No autonomous decisions.
- No sensitive data in personal tools.
- AI supports PM/Ops judgment; it does not replace accountability.

Working mode:
If this interface can directly create or edit local files, make the changes directly under the repo path above. If it cannot directly access local files, provide exact save paths and full Markdown file contents or precise patch instructions. Do not create package dependencies, frontend code, backend code, databases, APIs, deployment configs, or app scaffolding unless explicitly requested.

Continuity rule:
Use `00_MASTER_CONTEXT/MASTER_CONTEXT.md` and `09_HANDOFFS/SESSION_HANDOFF.md` as source-of-truth files whenever they are available. Do not restart the project from scratch. End the phase by updating `09_HANDOFFS/SESSION_HANDOFF.md` with current status, files changed, decisions made, open items, and the next best prompt.

Current phase:
Phase 5: Prompt Library

Objective:
Build a Gemini-first, platform-agnostic prompt library that supports the workflow library while enforcing data safety, human review, and PM/Ops-quality outputs.

Work to perform:
1. Review:
   - `00_MASTER_CONTEXT/MASTER_CONTEXT.md`
   - `09_HANDOFFS/SESSION_HANDOFF.md`
   - `05_PROMPTS/PROMPT_LIBRARY.md`
   - `04_WORKFLOWS/WORKFLOW_LIBRARY.md`
   - `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`
2. Strengthen `05_PROMPTS/PROMPT_LIBRARY.md` into a practical library of reusable prompts.
3. Add prompt patterns and copy-paste-ready prompts for the major workflows.
4. Include a prompt safety precheck for every prompt category.
5. Include placeholders rather than real data.
6. Make prompts usable in Gemini Enterprise first, but transferable to any approved enterprise AI tool.

Prompt library categories should include:

Scope clarification (per Phase 4 D-0034): The Phase 4 workflow library has 15 cards (W-01..W-15), but only 11 of them are AI-drafting workflows that need a dedicated paired prompt. The other four (W-04 schedule health, W-13 cross-tool mismatch, W-14 Google Workspace knowledge, W-15 clearance-limited onboarding) are structural, investigative, information-management, or personal-planning workflows and carry "Paired Phase 5 prompt: none" in their §15. The backlog defines exactly 11 Phase 5 prompt rows (A-0018, A-0019, A-0039..A-0047). Categories marked "no dedicated prompt" below stay in this list as a record of what was considered, but Phase 5 does not author prompts for them.

- Universal safety precheck prompt
- Weekly status report prompt (pairs with W-01; backlog A-0039)
- Meeting notes to action items prompt (pairs with W-02; backlog A-0040)
- Action item aging and follow-up prompt (pairs with W-03; backlog A-0041)
- Schedule health review prompt — no dedicated prompt (W-04 is structural; AI plays an identification role, not a drafting role)
- Schedule variance narrative prompt (pairs with W-05; backlog A-0047)
- EVM variance explanation prompt (pairs with W-06; backlog A-0018)
- Risk register cleanup prompt (pairs with W-07; backlog A-0042)
- Issue/discrepancy triage prompt (pairs with W-08; backlog A-0043)
- Project accounting reconciliation narrative prompt (pairs with W-09; backlog A-0019)
- Lessons learned capture prompt (pairs with W-10; backlog A-0046)
- SOP draft generation prompt (pairs with W-11; backlog A-0045)
- Executive brief generation prompt (pairs with W-12; backlog A-0044)
- Cross-tool mismatch investigation prompt — no dedicated prompt (W-13 is investigative; AI proposes candidate causes, not drafts)
- Google Workspace knowledge workflow prompt — no dedicated prompt (W-14 is information-management; AI's role is structural)
- Clearance-limited onboarding support prompt — no dedicated prompt (W-15 is personal-planning; AI's role is optional structuring)
- Prompt critique / output QA prompt

Each prompt should include:
- Use case
- Safe input requirements
- Prohibited input warning
- Copy-paste prompt text
- Expected output
- Human review checklist
- Notes for approved-tool migration

Constraints:
- Do not embed real employer data examples.
- Use fictional placeholders such as `[SYNTHETIC_PROJECT_NAME]`, `[APPROVED_INPUT]`, `[FICTIONAL_VARIANCE]`, and `[PLACEHOLDER_OWNER]`.
- Do not write prompts that ask the model to make final project decisions.
- Do not create autonomous agents or background processes.

Deliver:
- Updated `05_PROMPTS/PROMPT_LIBRARY.md`
- Optional prompt-specific files only if needed for readability
- Optional update to `04_WORKFLOWS/WORKFLOW_LIBRARY.md` for cross-references
- Updated `09_HANDOFFS/SESSION_HANDOFF.md`
- Short summary of what changed
- Next best prompt for Phase 6
```
