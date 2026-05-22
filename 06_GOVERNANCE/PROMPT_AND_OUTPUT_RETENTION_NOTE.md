# PROMPT_AND_OUTPUT_RETENTION_NOTE.md

## Purpose

A conservative posture on retaining prompts and AI outputs while employer retention policy is unknown. Once employer guidance exists for prompts and AI-generated outputs, this file gives way to that guidance.

This is personal preparation material. It does not state employer retention policy. It does not give legal advice.

## Conservative defaults

Until employer policy is known, default to the more restrictive option whenever a choice exists.

- **Synthetic and public prompts/outputs.** Retain in the repo. Treat the repo's commit history as the audit trail. There is no need to delete these.
- **Tom-personal prompts/outputs.** Retain only if useful for personal preparation. Do not retain inside any employer system as if they were employer content. If a personal prompt or output starts to resemble employer material, redact and resave or delete.
- **Employer-approved prompts/outputs.** Retain only inside the approved employer environment, under whatever retention rule applies to the underlying data. Never copy them into ATLAS or a personal tool for "backup."
- **Prohibited prompts/outputs.** Do not create them. If one is accidentally created (e.g., a paraphrase that turned out to be restricted), delete it from every place it landed and note the event in personal preparation so the workflow that produced it can be hardened.

## Operating rules for ATLAS

These rules apply to anything inside this repo and to any personal AI session that produces ATLAS-style content.

- Synthetic and public prompts and outputs may live indefinitely in the repo and in personal AI tool history.
- Tom-personal prompts and outputs may live in the repo and in personal AI tool history, but should be reviewed periodically and trimmed when they no longer add value.
- No prompt or output that originated from employer data lives in ATLAS or in a personal AI tool. Full stop.
- When a personal preparation workflow is later approved for employer use, the prompts and outputs created inside the approved employer environment do not flow back into ATLAS.

## Operating rules for personal AI tools

For personal AI tools (Claude consumer, ChatGPT consumer, Gemini consumer, etc.):

- Assume conversations are stored by default by the vendor.
- Assume conversation history can be searched and reviewed by Tom; do not assume it is private to a single session.
- Do not use personal AI tools with anything Tom-personal that could embarrass or harm a third party if it were later read.
- Periodically prune personal AI tool history of stale or sensitive Tom-personal items.
- If a vendor offers "do not train on my data" or "delete history" settings, prefer the more restrictive option for any Tom-personal use.
- Do not paste anything that even resembles restricted employer material into a personal AI tool, in any form.

## Operating rules to apply once an employer environment is in scope

These rules will be re-validated against actual employer policy when that policy is known.

- Treat prompts as records. If the output is a record, the prompt that produced it is part of the audit trail.
- Save prompts and outputs in the approved venue (the approved AI tool's workspace, the approved Workspace document, the approved repository), not in personal tools.
- Label AI-assisted documents where the employer convention requires it.
- Apply the same retention period to AI prompts and outputs that applies to the underlying source data, unless an explicit retention rule for AI material exists.
- For Strict-intensity reviews (see `HUMAN_REVIEW_AND_AUDITABILITY_MODEL.md`), retain the source, prompt, raw AI output, reviewer edits, reviewer sign-off, and accountable owner approval together.
- If an output is used externally (customer, partner, audit), capture the prompt and the reviewed output together; do not retain only the final external artifact.

## Deletion rules

- Delete from personal AI tools any conversation that no longer serves a personal preparation purpose, especially if it includes Tom-personal content.
- Delete from ATLAS any file that drifts toward employer-specific content. Replace with a synthetic version if the underlying pattern is still useful.
- Do not delete records from employer systems on your own initiative; that is the employer's policy domain.
- When in doubt about whether to delete an employer-environment record, do not delete; ask whoever owns the retention rule.

## What to do if a retention rule is unclear

Order of action:

1. Default to the more restrictive option (shorter retention, less duplication, no copy into personal tools).
2. Ask the right owner (IT, security, compliance, or the program reporting lead, depending on the data category).
3. Capture the answer in personal preparation notes; if it changes ATLAS posture, log it in `10_DECISION_LOG/DECISION_LOG.md`.
4. Revise this file when employer guidance becomes available.

## Things to avoid

- "I'll keep a copy in my personal tool just in case." That copy is the problem.
- Long-running personal AI conversations that accumulate Tom-personal context over months. Prune.
- Using personal cloud storage to back up employer-environment AI outputs.
- Renaming a sensitive prompt to hide its origin. The retention rule follows the content, not the filename.
- Assuming "ephemeral" or "incognito" AI modes prevent retention. Default to the assumption that anything you send to a vendor is retained somewhere.

## Revisit triggers

Revisit this file when any of the following happens:

- Employer policy on AI prompt or output retention becomes known (in part or in full).
- A vendor changes its retention or training policy in a way that affects current ATLAS use.
- A new audit category is introduced by the employer (e.g., AI-assisted output requires labeling).
- ATLAS produces its first employer-deployable artifact and a real retention path needs to be defined.

Until then, the posture above is the default.
