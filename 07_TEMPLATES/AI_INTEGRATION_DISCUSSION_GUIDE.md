# AI_INTEGRATION_DISCUSSION_GUIDE.md

## Artifact identity

- **Backlog ID:** (utility template - not a new backlog row, per D-0043)
- **Phase:** 6 - First-Week Readiness Kit
- **Operating workflow:** `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`
- **Kit index:** `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`
- **Status:** Ready for personal use
- **Last updated:** 2026-05-23

## Purpose

Conservative talking points Tom uses in early conversations about AI integration. The goal is to be a credible PM/Ops voice on responsible AI - not to advocate for any specific tool, not to assume authority, and not to position oneself as the AI policy owner. This file is the kit-layer companion to `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`; the governance file is the parent reference and is not restated here.

## Governance envelope

- **Data category** (per `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, "Data categories"): Public-or-synthetic for the guide itself; conversation answers Tom captures are Tom-personal and stay in personal preparation notes.
- **Tool environment** (same file, "Tool environments"): ATLAS-local Markdown.
- **Review intensity** (per `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, "Three review intensities"): Light. Tom self-reviews before each conversation.
- **Per-domain review pattern** (same file, "Per-domain review patterns"): Status and reporting outputs (when summarizing what was discussed).

## Use posture

- Listen before proposing.
- AI is one tool among many; human judgment and accountability are the point.
- Employer policy and approved tools come first; personal preferences last.
- Synthetic and public material is safe to discuss; employer specifics are not.
- "I don't know" is a complete answer.
- The job is PM/Ops value, of which responsible AI integration is one part.

## Tom's framing (when asked "what do you bring on AI?")

Use a short, calibrated answer. Adapt to venue and audience. Examples:

- "I treat AI as a drafting and structuring tool that improves PM/Ops outputs when there is a named human reviewer and approved data flow. My posture is conservative on tools, conservative on data, and audit-friendly on output."
- "I have a personal-preparation system of generic workflows and prompts I built before starting. I use synthetic data only. I would not bring any of that to employer data without approval."
- "On responsible AI integration I lean on three principles: human-in-the-loop on every output, approved tools only for real data, and synthetic demos for anything exploratory."

What to avoid: tool advocacy, naming specific personal AI products, claiming any internal AI authority, promising outcomes that depend on approvals that do not exist.

## What to bring to early conversations

When the conversation invites it - never unprompted in week one - Tom can offer:

1. A short verbal summary of how AI fits into PM/Ops workflows responsibly (see "Tom's framing" above).
2. The ATLAS distinction between personal-preparation artifacts and employer-deployable artifacts (see `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`, D-0026).
3. The six-step AI tool approval pattern (`06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, D-0025) - cited as a personal approach, never as employer policy.
4. The three review intensities and the per-domain review patterns (`06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, D-0023) - cited as how Tom personally treats AI output.
5. Synthetic demos (from a future Phase 7 demo pack, or current paired prompts/workflows) framed as patterns, not products.

## What not to bring

Hard "do not" list - mirrors `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md` "Hard 'do not' list":

- Do not claim knowledge of Motorola Solutions internal AI policy.
- Do not recommend bypasses, unofficial accounts, personal uploads, or unsanctioned integrations.
- Do not demonstrate AI tooling on real employer data.
- Do not pull internal screenshots, exports, or filenames into a demo.
- Do not use a personal AI account to summarize anything restricted, even paraphrased.
- Do not frame AI as a replacement for any role, especially the role of the person Tom is talking to.
- Do not speak in absolutes about AI capability or limitation; use measured language.
- Do not promise outcomes that depend on tool approvals that do not yet exist.
- Do not push a tool because it is what Tom personally prefers.

## Conversational openers Tom can reuse

Short, low-commitment phrases:

- "I'm trying to figure out the right way to integrate AI into PM/Ops work here, and I'd rather start with what the approved boundary looks like before proposing anything."
- "My posture is conservative: human review on every output, approved tools only for real data, and synthetic demos for anything exploratory."
- "I have some synthetic demos I built before starting; happy to walk one if it's useful, but I'm not asking to deploy anything."
- "Where I'm uncertain is around [topic]; do you know who owns that, or where I should look?"
- "Got it; I'll treat that as the boundary until I hear differently."

## Talking points Tom can adapt by audience

The substance does not change; the emphasis does. Pulls from `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md` "Audience-specific patterns."

- **Manager:** Frame AI work as scoped to whatever the approved boundary turns out to be. Offer one synthetic demo. Ask who in IT or security should be looped in before any real-data pilot.
- **IT:** Demonstrate the difference between tool capability and tool approval. Ask about the approved tool list, request process, and data categories that are off-limits regardless of tool.
- **Security:** Show Tom has a data classification model and a review pattern - cite them as personal preparation, not employer policy. Ask about restricted categories and reportable events.
- **Compliance:** Demonstrate that AI output is treated as a draft until reviewed. Ask about retention, labeling, and reviewer loop-ins.
- **Program leadership:** Frame AI as supporting reporting quality, schedule integrity, and discrepancy resolution. Use synthetic examples only. Ask which reporting cycle parts they would most want improved.

## Using synthetic demos in a conversation

When a synthetic demo helps:

1. State clearly, before opening it, that it is fictional and uses invented data.
2. Walk through it as a pattern (input → AI step → human review → output), not as a finished product.
3. Highlight the human review step explicitly.
4. Acknowledge the limits ("this is what it looks like on synthetic data; real data would need approvals and a different tool").
5. Stop on time.

Never blend a synthetic demo with real data on the fly to "make it more realistic." That defeats the purpose and violates the safety boundary.

## When the conversation drifts

- If someone pressures Tom to use AI on data Tom would classify as Prohibited: name the classification, name the model used to reach it, defer to the approval owner. Do not promise to revisit "later."
- If someone reads Tom's AI interest as advocacy for replacing roles: clarify directly. "AI doesn't replace the reviewer; it gives them a better draft to review."
- If someone speculates about policy Tom does not know: acknowledge the limits of what he knows. Do not fill the gap.
- If someone shares restricted information that would not be appropriate to put into any AI tool: do not transcribe it later into ATLAS, into a personal tool, or anywhere else.

## After the conversation

- Capture only generic, non-sensitive answers in personal preparation notes.
- If an answer changes ATLAS posture (a new constraint, a new tool category, a new approval gate), log it in `10_DECISION_LOG/DECISION_LOG.md`.
- If an answer changes open items, update `09_HANDOFFS/SESSION_HANDOFF.md`.
- Do not store specific data categories tied to specific programs, named policy exceptions, or internal contacts who asked not to be cited.

## Cross-references

- Parent governance reference (this file does not restate it): `06_GOVERNANCE/AI_CONVERSATION_GUIDE.md`.
- Governance bundle: `06_GOVERNANCE/AI_GOVERNANCE_NOTES.md`, `06_GOVERNANCE/DATA_SENSITIVITY_DECISION_MODEL.md`, `06_GOVERNANCE/HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`, `06_GOVERNANCE/AI_TOOL_APPROVAL_STRATEGY.md`, `06_GOVERNANCE/EMPLOYER_TOOL_APPROVAL_QUESTION_SET.md`, `06_GOVERNANCE/PROMPT_AND_OUTPUT_RETENTION_NOTE.md`.
- Operating workflow: `04_WORKFLOWS/W-15-clearance-limited-onboarding.md`.
- Kit index: `07_TEMPLATES/FIRST_WEEK_READINESS_KIT.md`.
- Onboarding question set (where AI-tool questions live in interview-ready form): `07_TEMPLATES/ONBOARDING_QUESTION_SET.md`.
- Discovery script (where AI workflow discovery questions originate): `07_TEMPLATES/FIRST_WEEK_DISCOVERY_SCRIPT.md`.
- Decision log: D-0043 (utility-template status of this file).
