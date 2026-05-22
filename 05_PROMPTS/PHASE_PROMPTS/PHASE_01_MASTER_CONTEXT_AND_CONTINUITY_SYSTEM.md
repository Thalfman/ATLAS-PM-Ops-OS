# Phase 01 Prompt - Master Context and Continuity System

## Phase

Phase 1: Master Context and Continuity System

## Purpose

Harden the durable context, session handoff process, and local skills so future sessions continue cleanly and safely.

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
Phase 1: Master Context and Continuity System

Objective:
Strengthen the source-of-truth and continuity mechanics so every future ATLAS session can resume without restarting, stay within the safety boundary, and keep outputs aligned to Tom's PM/Ops value proposition and expected responsible AI integration role.

Work to perform:
1. Review and strengthen `00_MASTER_CONTEXT/MASTER_CONTEXT.md` so it becomes the durable source of truth for the project.
2. Strengthen `09_HANDOFFS/SESSION_HANDOFF.md` so it clearly reflects current status, phase, files created, decisions, risks, open items, and next best prompt.
3. Strengthen `09_HANDOFFS/SESSION_HANDOFF_TEMPLATE.md` into a reusable continuity template.
4. Review the three local skill files and refine them only as needed:
   - `skills/atlas-planner/SKILL.md`
   - `skills/atlas-artifact-writer/SKILL.md`
   - `skills/atlas-session-handoff/SKILL.md`
5. Add a simple session-start and session-end protocol.
6. Make the continuity protocol practical for both local-agent usage and chat-only usage.

Required content elements:
- Project purpose and ATLAS definition.
- Tom's role positioning and value proposition.
- Clearance-limited onboarding context.
- Responsible AI integration as a major expected value area.
- Tool assumptions: Gemini-first, Google Workspace likely, Microsoft Project used, platform-agnostic migration path.
- Hard safety boundary and prohibited data categories.
- Human-in-the-loop operating model.
- Source-of-truth rule: MASTER_CONTEXT + SESSION_HANDOFF.
- Phase list from 0 through 12.
- Definition of done for future sessions.

Constraints:
- Do not create new folders unless clearly needed.
- Do not add software scaffolding.
- Do not invent employer systems, policies, program names, or internal processes.
- Keep the writing operational and concise enough to use.

Deliver:
- Updated `00_MASTER_CONTEXT/MASTER_CONTEXT.md`
- Updated `09_HANDOFFS/SESSION_HANDOFF.md`
- Updated `09_HANDOFFS/SESSION_HANDOFF_TEMPLATE.md`
- Optional light updates to the three `skills/*/SKILL.md` files if needed
- Short summary of what changed
- Next best prompt for Phase 2
```
