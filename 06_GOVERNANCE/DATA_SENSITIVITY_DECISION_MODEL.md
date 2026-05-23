# DATA_SENSITIVITY_DECISION_MODEL.md

## Purpose

A short, repeatable model for classifying a candidate input before any AI session, and routing it to a tool environment that is appropriate for that data category.

The model is conservative by design: when in doubt, it routes data to the more restrictive option. It exists so Tom can answer "is this safe to put into this tool?" in seconds, with the same logic every time.

This file does not state employer policy. It is personal preparation material. Any conflict with an explicit employer instruction is resolved in favor of the employer instruction.

## Data categories

Every candidate input falls into exactly one of these categories. If two seem to apply, use the more restrictive category.

| Category | What it includes | Examples |
|---|---|---|
| **Synthetic** | Fictional content authored by Tom or clearly invented for ATLAS use. | A made-up project with invented names, dates, and figures. The fictional schedule in `08_SYNTHETIC_DEMOS/`. |
| **Public** | Information that is published and broadly available without restriction. | Published news articles, PMI/PMBOK language, public training material, vendor documentation that is on the public web. |
| **Tom-personal** | Tom's own personal notes, observations, and preparation material that contains no employer data. | Tom's own learning notes, his own resume, his own draft questions for an employer conversation. |
| **Employer-approved** | Employer data that has been explicitly approved for the specific AI tool and use case, in writing or by documented practice. | A document where the employer policy or written approval allows that document to be processed by the approved AI tool. |
| **Prohibited** | Any data that is classified, CUI, ITAR/export-controlled, proprietary, customer, contract, internal schedule, internal finance, internal technical, real meeting note, real project accounting export, real Microsoft Project file, real internal report, or otherwise not approved for the tool in question. | Anything not on the public web that came from inside an employer system without explicit approval. |

Default rule: if a category cannot be determined with confidence, treat the input as **Prohibited** until that changes.

## Tool environments

Each input category routes to a tool environment.

| Environment | What it is | Acceptable inputs |
|---|---|---|
| **ATLAS-local Markdown** | This repo, edited in any text-capable tool. | Synthetic. Public. Tom-personal. |
| **Personal AI tool** | Tom's personal Claude, ChatGPT, Gemini consumer, etc. | Synthetic. Public. Tom-personal. Never employer-approved or prohibited. |
| **Employer-approved AI tool, approved data only** | The specific tool (Gemini Enterprise is the assumed default) that the employer has approved for the specific employer data category. | Synthetic. Public. Employer-approved (matched to the tool's approved scope). |
| **No AI tool** | A non-AI process, or no automation at all. | Prohibited (do not use AI on it). Any input where the data path or tool approval is uncertain. |

## Classification flow

For each candidate input, run through these questions in order. Stop at the first definitive answer.

1. **Is this Tom-authored fictional content or invented for ATLAS?** → Synthetic.
2. **Is this published and freely available to the public without restriction?** → Public.
3. **Is this Tom's own personal note or observation with no employer data?** → Tom-personal.
4. **Is this employer data that has explicit approval for this specific AI tool and use case?** → Employer-approved.
5. **None of the above clearly applies.** → Prohibited.

If the input is mixed (a synthetic document that contains a few real names, or a Tom-personal note that paraphrases something from a restricted briefing), split or redact it before classifying. The whole input takes the most restrictive category of any of its parts.

## Routing rules

Once the input is classified, route it as follows.

| Input category | Allowed environments |
|---|---|
| Synthetic | ATLAS-local Markdown. Personal AI tool. Employer-approved AI tool. |
| Public | ATLAS-local Markdown. Personal AI tool. Employer-approved AI tool. |
| Tom-personal | ATLAS-local Markdown. Personal AI tool. Not stored inside an employer system as if it were employer content. |
| Employer-approved | Only the specific employer-approved AI tool that the data is approved for, within the approved scope. Never a personal AI tool. Never ATLAS-local if the data lives only inside employer systems. |
| Prohibited | No AI tool. Use a non-AI process or stop. |

If the same workflow needs to combine inputs from more than one category, the combined workflow takes the most restrictive category.

## Worked examples

These examples are intentionally generic so they remain safe.

- **Example 1.** Tom drafts a fictional weekly status report for a made-up project to practice executive summarization. Classification: Synthetic. Allowed in any environment, including ATLAS-local Markdown and a personal AI tool.
- **Example 2.** Tom reads a public PMI article and wants a summary as study material. Classification: Public. Allowed in any environment.
- **Example 3.** Tom writes his own preparation notes about how he plans to approach his first week, with no employer specifics. Classification: Tom-personal. Allowed in ATLAS-local Markdown and a personal AI tool. Not stored in employer systems as if it were employer material.
- **Example 4.** Tom is offered an internal document during onboarding and wonders whether to run it through an AI tool. Classification: Treat as Employer-approved only if explicit approval exists for that tool and that data category; otherwise Prohibited. When in doubt, no AI tool.
- **Example 5.** Tom remembers details from a restricted briefing and considers paraphrasing them into a personal note for AI summarization. Classification: Prohibited. The data is restricted regardless of whether it is paraphrased, partial, or in Tom's own words.

## Things that look safer than they are

These framings often produce wrong classifications. Watch for them.

- "I'll just paraphrase it." Paraphrased restricted content is restricted content.
- "It's only a screenshot." Screenshots of internal systems are restricted content.
- "Only the filename is internal." Filenames can reveal program names, customer codes, or contract identifiers.
- "It's already in the public domain somewhere." If you cannot point to the public source, treat as not public.
- "It's a fictionalized version of something real." If a real reader could identify the real thing, treat as restricted.
- "It's just metadata." Metadata can be sensitive (timestamps, authors, organization names, locations).

## When this model conflicts with explicit employer guidance

Employer guidance wins. If an employer instruction says "do not use AI on category X" and this model would allow it, do not use AI on category X. If an employer instruction explicitly permits something that this model treats as restricted, follow the employer instruction and update the personal `AI_GOVERNANCE_NOTES.md` and `DECISION_LOG.md` to reflect the new known information.

## How to use this file in a session

Before any AI session that touches a non-obvious input:

1. State the input category in one line.
2. State the chosen environment in one line.
3. If either is uncertain, do not run the AI step.

Workflows in `04_WORKFLOWS/` (Phase 4) and prompts in `05_PROMPTS/` (Phase 5) should reference this file rather than re-defining the categories.
