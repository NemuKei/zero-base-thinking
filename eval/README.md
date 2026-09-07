# Behavioral evaluation

The cases in [cases.json](cases.json) are synthetic. They exercise Japanese dialogue for skill design, a business idea, a new concept, scope preservation, explanation repair, session adaptation, and pauses. They are not transcripts from real users.

The focused [opening cases](opening-cases.json) add open-ended invocation with rich or sparse context, bare invocation, a proposal-first request, and an ordinary-task guard. The [v0.1.1 opening report](results/2026-09-06-opening/report.md) compares the changed default with v0.1.0 where relevant and records the requested model settings and criterion-level judgments.

The [direction and purpose cases](direction-cases.json) cover a purpose-confirmation opening, an unknown current purpose, independent ways to deliver an established value, comparison with the current arrangement, official-source uncertainty, and fixed constraints. The [v0.1.2 report](results/2026-09-08-directions/report.md) records focused response samples and a scripted purpose-correction continuation. This is separate from a complete-conversation evaluation.

The [complete-conversation cases](conversation-cases.json) add three paired dialogues with separate assistant and simulated-user roles: purpose recovery, a sound current arrangement, and a proposal-first request with fixed constraints. The [complete-conversation report](results/2026-09-08-conversations/report.md) records all six transcripts through an ordinary edit, comparison differences, and an independent review. Human-perceived usefulness remains unmeasured; the [protocol](results/2026-09-08-conversations/protocol.md) explains the simulation limits.

## Running a sample

Use one fresh context per case. Provide only the case's `context`, `user`, and any `source_context` as the simulated conversation. Do not give the actor its `checks`, the rubric, worked examples, or earlier outputs. Supply a scripted continuation only after the first response is saved.

- **Control:** no Zero-Base Thinking instructions.
- **With skill:** load `skills/zero-base-thinking/SKILL.md` and its linked question guide when relevant. Continuation cases retain the fact that the user invoked the skill earlier.
- **Negative activation:** present only the skill name and description as discoverable metadata. Do not force-load the body and then claim to have tested discovery.

Ask for the assistant's next response. Save it verbatim as an artifact. Do not send the synthetic question to a real user or execute the simulated project's actions. This checks response behavior; it does not test the live question UI.

A suitable actor instruction is:

> Read the supplied conversation and, where this arm includes it, the skill and its linked question guide. Produce the next assistant response in the user's language. Do not read evaluations, worked examples, other responses, or unrelated files. Do not execute the simulated work. Save the exact response without self-evaluation.

## Review criteria

Judge the meaning of the response, not whether it repeats a keyword or a heading.

| Check family | Evidence to look for |
| --- | --- |
| Activation | An explicit request starts the workflow; routine work or frustration alone does not. |
| Question purpose | The user can tell why the question matters and what their answer changes. |
| Consequences | Alternatives describe a concrete future experience or next inquiry, a material burden where relevant, and uncertainty. |
| Help and freedom | Asking for an explanation, being undecided, or answering outside the options is supported. |
| Comprehension repair | An explanation request produces simpler consequences or an example, with the decision still pending. |
| Adaptation | Explicit preferences and explanation requests change subsequent wording without a competence label, a fixed failure threshold, or unrequested memory writes. |
| Reframing | Documents and previous decisions are reconsidered as evidence; a new insight can change the question. |
| Purpose | The opening checks a tentative intended value or elicits it when unknown. A purpose already settled in the current exchange is carried forward; an inherited definition is not presumed to be agreement. |
| Blank sheet | Once enough input exists, a positive construction from reconsidered value and constraints is shown before reuse or a final recommendation. |
| Options and comparison | Options come from different ways to deliver the established value. Benefits, burdens, and uncertainty are comparable; the current arrangement is located afterward, with transition costs assessed separately. |
| Scope | Current user-specified constraints remain intact. |
| Epistemic care | Observations, user intentions, and causal or commercial hypotheses are distinguished; metrics and evidence are not invented. |
| Neutral decision | The response does not equate zero-base thinking with a rewrite, or automatically privilege preservation. |
| Pause and authority | Silence, a countdown, or an initial selection is not agreement; proposed thinking does not authorize live changes. |

Use `pass`, `partial`, `fail`, or `not_applicable` for each relevant check, supported by a short reason and a quoted response excerpt when useful. Record uncertainties. A first turn that asks an essential question is an unfinished conversation, not a failed final-design test. A response that promises a future blank-sheet pass has not completed that pass.

## Evidence and limits

Keep raw responses, the actor setup, evaluated file hashes, and case-specific judgments with each report. A passing control is useful evidence that the capability already existed; do not relabel it as a baseline failure. Small samples do not establish statistical improvements or certify all models.

Add a fresh case when a demonstrated gap or new requirement justifies it. Re-run affected cases after behavior changes. Repeat samples or add hosts when the uncertainty being investigated warrants that cost.

The [v0.1.0 local report](results/2026-09-06/report.md) and [v0.1.1 opening report](results/2026-09-06-opening/report.md) are historical evidence. Their source bytes are pinned to snapshot revisions so later changes do not silently inherit old pass claims. Live UI behavior, host discovery, persistent memory integrations, and multi-agent orchestration require separate end-to-end checks before claiming support has been verified.

## Installation checks

The [native Codex CLI check](results/2026-09-08-installation/report.md) verifies v0.1.2 user-wide installation from the public repository, TUI selection, direct invocation, Japanese routing from another project, and an ordinary edit on macOS. Its fresh local profile reused an existing account; other native clients and operating systems remain unverified.

The [current distribution record](distribution.json) identifies its artifact version, tested scope, and runtime-file hashes. The [archived v0.1.1 record](results/2026-09-06-opening/distribution-0.1.1.json) covers that version's local Codex project copy. The [archived v0.1.0 record](results/2026-09-06/distribution-0.1.0.json) covers the earlier local-folder, ZIP, and public-repository checks, including Codex and Claude Code project installations. Each installed package contained five files; the original root-level layout had copied 27.

CLI telemetry and external audit requests are disabled during recorded installation checks. File-copy checks alone do not establish native discovery or invocation; the native record names its verified client and environment. Refer to each record rather than extending its results to other versions, clients, or operating systems.
