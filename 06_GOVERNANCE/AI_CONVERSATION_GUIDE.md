# AI_CONVERSATION_GUIDE.md

## Purpose

A safe pattern for discussing AI integration with management, IT, security, compliance, or program leadership in a federal/defense-adjacent environment. The goal is to be a credible PM/Ops voice on responsible AI, not to advocate for any specific tool, and not to position oneself as the AI policy owner.

This file is personal preparation material. It does not state employer policy. It does not give legal advice. It does not authorize anything.

## Default stance

- AI is one tool among many.
- Human judgment and accountability are the point; AI is in support.
- Employer policy and approved tools come first.
- Synthetic and public material is safe to discuss; employer specifics are not.
- "I don't know" is a complete answer.
- The job is to add PM/Ops value, of which responsible AI integration is one part.

If the conversation drifts away from those defaults, redirect or wind it down.

## Hard "do not" list

Do not:

- Claim knowledge of Motorola Solutions internal AI policy.
- Recommend bypasses, unofficial accounts, personal uploads, or unsanctioned integrations.
- Demonstrate AI tooling on real employer data.
- Pull internal screenshots, exports, or filenames into a demo.
- Use a personal AI account to summarize anything restricted, even paraphrased.
- Frame AI as a replacement for any role, especially the role of the person you are talking to.
- Speak in absolutes about what AI can or cannot do; use measured language.
- Speak about classified, CUI, or ITAR-related work in any AI-flavored context.
- Promise outcomes that depend on tool approvals that do not yet exist.
- Push a tool because it is what you personally prefer.

## Conversational moves that usually work

- Start with PM/Ops outcomes (reporting consistency, schedule integrity, action follow-through), not tools.
- Offer synthetic demos when illustration helps.
- Ask first; propose second.
- Restate what you heard before adding any new content.
- Use the data sensitivity language from `DATA_SENSITIVITY_DECISION_MODEL.md` when classification comes up.
- Cite `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md` when audit or accountability comes up.
- Acknowledge that AI policy may evolve and that today's answer can change.
- Defer to the person who actually owns the answer (IT, security, compliance, program lead).

## Audience-specific patterns

The framing changes by audience. The substance does not.

### Manager (1:1 or small team)

- Frame: "I want to use AI responsibly to improve PM/Ops outcomes; here is how I plan to stay inside whatever the approved boundary turns out to be."
- Show: a synthetic example of an output you could produce (status drafting, schedule narrative, action triage).
- Ask: who in IT or security should be in the loop before any real-data pilot; what manager-level approvals are expected.
- Avoid: tool advocacy; commitments before learning the approval path.

### IT

- Frame: "I want to understand the approved AI tool list and where I should be sending requests to expand it (or not)."
- Show: that you understand the difference between tool capability and tool approval.
- Ask: about the approved tool list, request process, expected timelines, and any data categories that are off-limits to AI tools regardless of approval status.
- Avoid: asking IT to make exceptions; treating IT as the policy authority on classified or contract data (that is usually elsewhere).

### Security

- Frame: "I want to be sure my personal preparation and any future workplace AI use stay inside the safety boundary."
- Show: that you have a data classification model and a human-review pattern (cite this file and its siblings as personal preparation, not as employer policy).
- Ask: about restricted data categories, audit expectations, and what would constitute a reportable event.
- Avoid: discussing specific incidents; speculating about what other employees do; describing classified or CUI work in any AI context.

### Compliance

- Frame: "I want to be sure AI-assisted PM/Ops work meets the audit and record-keeping expectations that already exist."
- Show: that you treat AI output as a draft until reviewed.
- Ask: about retention, labeling, recording, and who needs to be looped in for AI-assisted output that becomes part of the record.
- Avoid: framing compliance as a blocker; legal interpretation; specific contractual obligations you have not been briefed on.

### Program leadership

- Frame: "I want to support program reporting quality, schedule integrity, and discrepancy resolution; AI may help in some of that, with appropriate guardrails."
- Show: how a human-reviewed AI-assisted narrative is more reliable than an ad-hoc draft, using synthetic examples.
- Ask: which areas of the program reporting cycle the leadership wants to improve, and whether AI-assisted drafting is in scope for any of them.
- Avoid: claiming AI will fix program problems; recommending tools that touch program data without an approval path.

## Talk tracks

Short, reusable openings. Adapt for the venue.

- "I'm trying to figure out the right way to integrate AI into PM/Ops work here, and I'd rather start with what the approved boundary looks like before proposing anything specific."
- "My posture is conservative: human review on every output, approved tools only for real data, and synthetic demos for anything I'm exploring."
- "I have some generic synthetic demos I built before starting; happy to show one if it's useful, but I'm not asking to deploy anything."
- "Where I'm uncertain is around [topic]; do you know who owns that or where I should look?"
- "Got it; I'll treat that as the boundary until I hear differently."

## How to use synthetic demos in a conversation

Synthetic demos under `08_SYNTHETIC_DEMOS/` exist specifically for these conversations. When you use one:

1. State clearly, before opening it, that it is fictional and uses invented data.
2. Walk through it as a pattern (input → AI step → human review → output), not as a finished product.
3. Highlight the human review step explicitly.
4. Acknowledge the limits ("this is what it looks like on synthetic data; real data would need approvals and a different tool").
5. Stop on time.

Never blend a synthetic demo with real data on the fly to "make it more realistic." That defeats the purpose.

## What to do when the conversation goes sideways

- If someone pressures you to use AI on data you would classify as Prohibited: name the classification, name the model you used to reach it, and defer to whoever owns the approval. Do not promise to revisit "later."
- If someone misreads your interest in AI as advocacy for replacing roles: clarify directly. "AI doesn't replace the reviewer; it gives them a better draft to review."
- If someone speculates about policy you do not know: acknowledge the limits of what you know. Do not fill the gap.
- If someone shares restricted information in the conversation in a way that would not be appropriate to put into any AI tool: do not transcribe it later into ATLAS, into a personal tool, or into anything else. Treat it like any other restricted briefing.

## How to capture what you learn

After each meaningful conversation:

- Note non-sensitive answers in personal preparation only (a note in ATLAS is fine if the content is generic enough).
- If an answer changes ATLAS posture, log it in `10_DECISION_LOG/DECISION_LOG.md`.
- If an answer changes the open items in `09_HANDOFFS/SESSION_HANDOFF.md`, update the handoff.
- Do not store restricted detail (specific data categories tied to specific programs, named policy exceptions, internal contacts who asked not to be cited) in ATLAS.

## Reading the room

Signs the conversation should wind down:

- Repeated questions about specific tools or features (you are doing too much advocating).
- The other person referencing time pressure ("I have a hard stop").
- Tangents into legal or contractual territory you are not briefed on.
- The other person asking what you have already deployed.

In any of these cases, summarize what you heard, name one concrete next step (or zero), and end on time.
