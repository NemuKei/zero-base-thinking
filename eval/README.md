# Behavioral evaluation

The cases in [cases.json](cases.json) are synthetic. They exercise Japanese dialogue for skill design, a business idea, a new concept, scope preservation, explanation repair, session adaptation, and pauses. They are not transcripts from real users.

## Running a sample

Use one fresh context per case. Provide only the case's `context` and `user` fields as the simulated conversation. Do not give the actor its `checks`, the rubric, worked examples, or earlier outputs.

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
| Blank sheet | Once enough input exists, a positive construction from reconsidered value and constraints is shown before reuse or a final recommendation. |
| Scope | Current user-specified constraints remain intact. |
| Epistemic care | Observations, user intentions, and causal or commercial hypotheses are distinguished; metrics and evidence are not invented. |
| Neutral decision | The response does not equate zero-base thinking with a rewrite, or automatically privilege preservation. |
| Pause and authority | Silence, a countdown, or an initial selection is not agreement; proposed thinking does not authorize live changes. |

Use `pass`, `partial`, `fail`, or `not_applicable` for each relevant check, supported by a short reason and a quoted response excerpt when useful. Record uncertainties. A first turn that asks an essential question is an unfinished conversation, not a failed final-design test. A response that promises a future blank-sheet pass has not completed that pass.

## Evidence and limits

Keep raw responses, the actor setup, evaluated file hashes, and case-specific judgments with each report. A passing control is useful evidence that the capability already existed; do not relabel it as a baseline failure. Small samples do not establish statistical improvements or certify all models.

Add a fresh case when a demonstrated gap or new requirement justifies it. Re-run affected cases after behavior changes. Repeat samples or add hosts when the uncertainty being investigated warrants that cost.

The [2026-09-06 local report](results/2026-09-06/report.md) records the actual evaluation and its limits. Live UI behavior, host discovery, persistent memory integrations, and multi-agent orchestration require separate end-to-end checks before claiming support has been verified.

## Installation checks

The [distribution check record](distribution.json) covers `skills@1.5.23` local-folder installation for Codex and Claude Code in isolated project directories on macOS. Both initial installation and reinstall were exercised. Each destination contained exactly the five runtime-package files with matching SHA-256 hashes, rather than the 27 files copied by the original root-level layout.

The behavior instructions were relocated without changing their bytes; the earlier response report includes a map to their current locations. The installation checks do not establish user-global writes, remote installation, Windows/Linux behavior, or native agent-session discovery.
