# Role instructions used for the conversation samples

Paths below are placeholders for the frozen case, runtime, and each role's own output files. The six assistant roles were fresh contexts. Each simulated user was also a separate fresh context, then retained only that dialogue across turns. The instructions below capture the role contract; file paths and completion-only transport wording varied by dispatch.

## Assistant actor

Read only the supplied initial context and user request. Treat them as the user's conversation and produce the next assistant response in Japanese. In the skill arm, also read the frozen SKILL.md and its question guide. In the control arm, do not load skills or skill metadata.

Do not read worked examples, evaluation criteria, user persona files, other conversations, repositories, or personal history. Do not browse or execute the simulated project's work. Do not call the real user or question UI tools; use ordinary text dialogue. Save the exact assistant response without evaluation commentary or self-scoring. Return only a completion message to the parent. Further user messages may follow in the same conversation.

For subsequent turns, read only the newly delivered user message, keep the existing restrictions, and save the exact next assistant response.

## Simulated user

Act only as a fictional user in one offline dialogue, not as an evaluator or assistant. Read the case's user persona and the latest assistant reply. Use the persona's facts and adapt to what the assistant actually said. Reveal scenario facts only as relevant; do not invent observed events, measurements, user expertise, or tool capabilities.

Do not read skills, scoring criteria, arm mapping, other dialogues, or unrelated files. Do not reward an expected method or agree merely to finish. Do not contact a real user or execute anything in the scenario. When a usable direction or bounded next check has been agreed and confirmed, send the case's ordinary edit exactly as the next message. The maximum assistant turns is an evaluation ceiling, not a user answer deadline; do not fabricate agreement to meet it.

Write the exact natural Japanese user reply plus transport metadata: reply kind, facts released, and a brief explanation of the simulated response. The parent forwards only the reply text to the assistant. These fields describe simulation behavior, not a human's experience or competence.

For subsequent turns, use the same persona and restrictions with only that dialogue's new assistant response.

## Review

Review complete transcripts against the protocol and case facts. Assess intended value, meaningful alternatives, explanation repair, changed answers, a useful direction or bounded next check, and return to ordinary editing. Identify material failures, repeated or ignored questions, unsupported facts, and comparison confounds. Do not equate shorter replies, retention, rewriting, or quoting a rule with success. Simulated agreement is not human-perceived usefulness. Support judgments with exact turn references; do not edit transcripts or recommend runtime changes without a demonstrated failure.
